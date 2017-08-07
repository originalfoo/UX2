# UX2: Universal Extension Bus

> UNDER CONSTRUCTION - LIABLE TO CHANGE

UX2 is an open source, connector-agnostic, board-to-board communication bus which supports the following protocols (depending on pin variant):

## Quick Reference

There are four variants which determine the function of the outer pins...

**UX2-GPIO** – four GPIO  
![UX2-GPIO](./img/ux2-gpio.png)

**UX2-ALT** – two GPIO, one addtional I2C  
![UX2-ALT](./img/ux2-alt.png)

**UX2-1IS** – 1-Wire, Interrupt and Sound-Wire  
Note: Not suitable for hosts that rely on energy harvesting  
![UX2-1IS](./img/ux2-1is.png)

**UX2-I2C** – two additional I2C  
![UX2-I2C](./img/ux2-i2c.png)

### Pins

| UX2                                                   | Protocol          |
| ----------------------------------------------------- | ----------------- |
| ![3V3](../../pin/3v3.png) ![GND](../../pin/gnd.png)   | POWER             |
| ![!W](../../pin/1w.png)                               | 1-WIRE            |
| ![!INT](../../pin/int.png)                            | INTERRUPT         |
| ![!Gx](../../pin/g.png)                               | GPIO              |
| ![RXD](../../pin/rxd.png) ![TXD](../../pin/txd.png)   | UART / Asynch     |
| ![SDAx](../../pin/sda.png) ![SCLx](../../pin/scl.png) | I2C               |
| ![MISO](../../pin/miso.png) ![MOSI](../../pin/mosi.png) ![SCK](../../pin/sck.png) ![SSEL](../../pin/ssel.png)  | SPI |
| ![SWD](../../pin/swd.png) ![SWC](../../pin/swc.png)   | I2C               |

### Pin variant selection

There are two common ways to set the pin variant:

1. Hard-code via firmware on the MCU
2. Physical jumpers or dip switches (see below)

Two bits (`B0`, `B1`) are required to represent the 4 possible pin variants; easily achieved with jumpers or dip switches:

| B0 | B1 |  Pinout  |
| -- | -- | -------- |
| 0  | 0  | UX2-GPIO |
| 0  | 1  | UX2-ALT  |
| 1  | 0  | UX2-1IS  |
| 1  | 1  | UX2-I2C  |

Read setting with only one MCU IO? Use [R-2R resistor ladder](https://www.wikiwand.com/en/Resistor_ladder#/R.E2.80.932R_resistor_ladder_network_.28digital_to_analog_conversion.29) [DAC](https://www.wikiwand.com/en/Digital-to-analog_converter) to merge digital bits in to single analog value:

![2-bit DAC using R-2R resitor ladder](./img/2-bit-dac.png)

## [Protocols](./protocols/README.md)

* [GPIO](https://www.wikiwand.com/en/General-purpose_input/output) – General Purpose Input/Output
* [I2C](./protocols/i2c/README.md)
* [1-Wire](./protocols/1wire/README.md)
* [Interrupt](https://www.wikiwand.com/en/Interrupt) – wake master/host MCU via slave/module triggered interrupt
* [UART](https://www.wikiwand.com/en/Universal_asynchronous_receiver/transmitter) / [Async](https://www.wikiwand.com/en/Asynchronous_serial_communication) - serial communication bus
* [SPI](https://www.wikiwand.com/en/Serial_Peripheral_Interface_Bus)
* [Sound-Wire](https://www.mipi.org/specifications/soundwire)

## Modules

UX2 is compatible with hundreds of commercially available and open source modules. For more information, see [Modules](./modules/README.md).

### Sound-Wire components

**UX2-1IS pin variant**, with following wiring:

* `SWD` connects to `Data`
* `SWC` connects to `Clock` or `Clk`

Note: In circuit schematics, the clock connections are often omitted for sake of clarity (focus is on the data); the clock connection is always required regardless.

### RS232, RS485, IRDA, USB, SD/MMC

Use the UEXT bus (see UEXT section above) in conjunction with [Olimex Interface Modules](https://www.olimex.com/Products/Modules/Interface/).

Any pin variant can be used as they don't affect the UEXT pins.

## License

See [License](./LICENSE).
