# Adafruit devices

> Adafruit produce a wide range of breakout and sensor boards, all of which are open source and accompanied by extensive documentation and tutorials.

* [Adafruit breakout boards](https://www.adafruit.com/category/42)
* [Adafruit sesnor boards](https://www.adafruit.com/category/35)

## Pin variants

Adafruit boards use a variety of interfaces, most of which are GPIO and/or I2C/SPI.

UX2-GPIO – 4 x GPIO, 1 x UART, 1 x I2C, 1 x SPI:

![UX2-GPIO](../../img/ux2-gpio.png)

UX2-I2C – 3 x I2C, 1 x UART, 1 x SPI:

![UX2-I2C](../../img/ux2-i2c.png)

UX2-ALT – 2 x GPIO, 1 x UART, 2 x I2C, 1 x SPI:

![UX2-ALT](../../img/ux2-alt.png)

For devices that require I2S, use the UX2-GPIO pin variant and [configure the GPIOs for I2S](../I2S/README.md).

## Wiring

The wiring will depend on the devices you are connecting to, but generally:

| UX2                          | Adafruit              |
| ---------------------------- | --------------------- |
| ![3V3](../../pin/3v3.png)    | `Vin`, `Vcc` or `3Vo` |
| ![GND](../../pin/gnd.png)    | `GND`                 |
| ![SDAx](../../pin/sda.png)   | `SDA`                 |
| ![SCLx](../../pin/scl.png)   | `SCL`                 |
| ![MISO](../../pin/miso.png)  | `MISO`                |
| ![MOSI](../../pin/mosi.png)  | `MOSI`                |
| ![SCK](../../pin/sck.png)    | `SCK`                 |
| ![SSEL](../../pin/ssel.png)  | `SSEL`                |
| ![RXD](../../pin/rxd.png)    | `TXD` (not `RXD`)     |
| ![TXD](../../pin/txd.png)    | `RXD` (not `TXD`)     |
| ![Gx](../../pin/g.png)       | Remaining pins        |

Remember that each GPIO (`Gx`) pin can only be connected to one target device. Likewise, the UART (`RXD` and `TXD`) pins can only be connected to one device.

The I2C and SPI interfaces support chaining of multiple devices. Keep an eye on `3V3` pin current draw when chaining multiple devices.

## Host Considerations

TBC
