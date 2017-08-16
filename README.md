# UX2: Universal Extension Bus

> UNDER CONSTRUCTION - LIABLE TO CHANGE

UX2 is an open source, connector-agnostic, board-to-board communication bus. It supports multiple interface protocols, facilitating connection to a vast range of commerically available add-on modules from popular venodors.

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

See also: [Tips on pin variant selection](./pin/README.md)

### Pins / Protocols

| UX2                                           | Protocol                              |
| --------------------------------------------- | ------------------------------------- |
| ![!Gx](./pin/g.png)                           | GPIO                                  |
| ![!W](./pin/1w.png)                           | [1-WIRE](./protocols/1wire/README.md) |
| ![!INT](./pin/int.png)                        | INTERRUPT                             |
| ![3V3](./pin/3v3.png) ![GND](./pin/gnd.png)   | POWER                                 |
| ![RXD](./pin/rxd.png) ![TXD](./pin/txd.png)   | UART / Asynch                         |
| ![SDAx](./pin/sda.png) ![SCLx](./pin/scl.png) | [I2C](./protocols/i2c/README.md) / [SMBus](./protocols/smbus/README.md) |
| ![MISO](./pin/miso.png) ![MOSI](./pin/mosi.png) ![SCK](./pin/sck.png) ![SSEL](./pin/ssel.png)  | [SPI](./protocols/spi/README.md) |
| ![SWD](./pin/swd.png) ![SWC](./pin/swc.png)   | SOUND-WIRE                            |

## [Protocols](./protocols/README.md)

* [GPIO](https://www.wikiwand.com/en/General-purpose_input/output) – General Purpose Input/Output
* [Interrupt](https://www.wikiwand.com/en/Interrupt) – wake master/host MCU via slave/module triggered interrupt
* [UART](https://www.wikiwand.com/en/Universal_asynchronous_receiver/transmitter) / [Async](https://www.wikiwand.com/en/Asynchronous_serial_communication) - serial communication bus
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
