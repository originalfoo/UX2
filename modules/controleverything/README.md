# ControlEverything

> ControlEverything.com manufacturers hundreds of plug-and-play hardware devices for IoT applications such as Current Monitors, FET Drivers & Relay Controllers and much more!

* [Controllers](https://shop.controleverything.com/collections/controllers)
* [Sensors](https://shop.controleverything.com/collections/sensors)
* [Bus Handlers](https://shop.controleverything.com/collections/bus-handlers)

## Pin variants

For best results use their I2C boards, which are chainable, but be sure to use the Power Level Shifter (see "Wiring" section) to ensure 5V supply.

UX2-I2C – 3 x I2C, 1 x UART, 1 x SPI:

![UX2-I2C](../../img/ux2-i2c.png)

UX2-ALT – 2 x I2C, 2 x GPIO, 1 x UART, 1 x SPI:

![UX2-ALT](../../img/ux2-alt.png)

UX2-GPIO – 1 x I2C, 4 x GPIO, 1 x UART, 1 x SPI:

![UX2-GPIO](../../img/ux2-gpio.png)

UX2-1IS – 1 x I2C, 1 x 1-WIRE, 1 x INTERRUPT, 1 x UART, 1 x SPI, 1 x SOUND-WIRE:

![UX2-1IS](../../img/ux2-1is.png)

## Wiring

First, make sure you have a Power Level Shifter beween each UX2 I2C bus and the ControlEverything modules:

![Power Level Shifter](controleverything.png)

Then wire everything up in the usual I2C way...

| UX2                          | Control Everything |
| ---------------------------- | ------------------ |
| ![3V3](../../pin/3v3.png)    | `Vin`, `Vcc`       |
| ![GND](../../pin/gnd.png)    | `GND`              |
| ![SDAx](../../pin/sda.png)   | `SDA`              |
| ![SCLx](../../pin/scl.png)   | `SCL`              |

## Topology

I2C devices can be chained in a linear topology as shown above.

ControlEverything provide [Hubs](https://shop.controleverything.com/collections/bus-handlers) which allow more complex topologies.

## Host Considerations

TBC

## See also

* [UX2 Overview](../../README.md)
* [Modules](../README.md)
* [Protocols](../../protocols/README.md)
    * [I2C](../../protocols/i2c/README.md)