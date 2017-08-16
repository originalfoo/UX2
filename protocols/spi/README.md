#  SPI

> The Serial Peripheral Interface bus (SPI) is a synchronous serial communication interface specification used for short distance communication, primarily in embedded systems. SPI devices communicate in full duplex mode using a master-slave architecture with a single master. The master device originates the frame for reading and writing. Multiple slave devices are supported through selection with individual slave select (SSEL) lines.

* [Wikipedia Article](https://www.wikiwand.com/en/Serial_Peripheral_Interface_Bus)

## Pin Variants

All pin variants provide an SPI interface which has a single slave select pin (`SSEL`). If you need more slave selelects, the UX2-GPIO variant can be used; utilise it's `Gx` pins for up to 4 additional slave selects.

UX2-GPIO – 4 x GPIO, 1 x UART, 1 x I2C, 1 x SPI:

![UX2-GPIO](../../img/ux2-gpio.png)

UX2-1IS – 1 x 1-WIRE, 1 x INTERRUPT, 1 x UART, 1 x I2C, 1 x SPI, 1 x SOUND-WIRE:

![UX2-1IS](../../img/ux2-1is.png)

UX2-ALT – 2 x GPIO, 1 x UART, 2 x I2C, 1 x SPI:

![UX2-ALT](../../img/ux2-alt.png)

UX2-I2C – 3 x I2C, 1 x UART, 1 x SPI:

![UX2-I2C](../../img/ux2-i2c.png)

## Wiring

The SPI interface uses at least 6 wires, and GPIO `Gx` pins can be used as additional slave selects if required:

| UX2                         | SPI                           |
| --------------------------- | ----------------------------- |
| ![MISO](../../pin/miso.png) | `MISO` (master in, slave out) |
| ![MOSI](../../pin/mosi.png) | `MOSI` (master out, slave in) |
| ![SCK](../../pin/sck.png)   | `SCK` (slave clock)           |
| ![SSEL](../../pin/ssel.png) | `SS` (slave select)           |
| ![GPIO](../../pin/g.png)    | `SS` (use as exta `SSEL`)     |
| ![3V3](../../pin/3v3.png)   | `VCC`                         |
| ![GND](../../pin/gnd.png)   | `GND`                         |

## Topology

TBD

## See also:

* [UX2 Overview](../../README.md)
* [Protocols Overview](../README.md)
* [Modules](../../modules/README.md)
    * [Adafruit](../../modules/adafruit/README.md)
    * [Sparkfun](../../modules/sparkfun/README.md)
    * [UEXT](../../modules/uext/README.md)
