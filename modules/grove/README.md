# Grove Modules (Seeed Studio)

> Grove is a modular, standardized connector prototyping system. Grove takes a building block approach to assembling electronics.

* [Grove System Overview](http://wiki.seeed.cc/Grove_System/)
* [Grove Modules](https://www.seeedstudio.com/category/Grove-c-1003.html)

## Pin variants

Grove modules use a variety of interfaces including GPIO (analogue / digital), I2C and UART.

UX2-GPIO - 4 x GPIO, 1 x UART, 1 x I2C, 1 x SPI:

![UX2-GPIO](../../img/ux2-gpio.png)

UX2-I2C – 3 x I2C, 1 x UART, 1 x SPI:

![UX2-I2C](../../img/ux2-i2c.png)

UX2-ALT – 2 x GPIO, 1 x UART, 2 x I2C, 1 x SPI:

![UX2-ALT](../../img/ux2-alt.png)

## Wiring

The wiring will depend on the devices you are connecting to, but generally:

| UX2                          | Grove                      |
| ---------------------------- | -------------------------- |
| ![3V3](../../pin/3v3.png)    | `VCC` (pin 3, red wire)    |
| ![GND](../../pin/gnd.png)    | `GND` (pin 4, black wire)  |
| ![SDAx](../../pin/sda.png)   | `SDA` (pin 2, white wire)  |
| ![SCLx](../../pin/scl.png)   | `SCL` (pin 1, yellow wire) |
| ![RXD](../../pin/rxd.png)    | `TX`  (pin 2, white wire)  |
| ![TXD](../../pin/txd.png)    | `RX`  (pin 1, yellow wire) |
| ![Gx](../../pin/g.png)       | `Dn`  (pin 1 and 2)        |
| ![Gx](../../pin/g.png)       | `An`  (pin 1 and 2)        |

Remember that each GPIO (`Gx`) pin can only be connected to one target analogue or digital device. Such devices usually have two pins of the same type. For example: Digital device has `D0` (pin 1, yellow wire) and `D1` (pin 2, white wire). Analogue devices work in a similar way.

The UX2 UART (`RXD` and `TXD`) pins can only be connected to one device.

The I2C interface supports chaining of multiple devices. Keep an eye on `3V3` pin current draw when chaining multiple devices.

## Host Considerations

Ensure GPIO (`Gx`) pins support ADC/DAC and PWM.

## See also

* [UX2 Overview](../../README.md)
* [Modules](../README.md)
* [Protocols](../../protocols/README.md)
