# Adafruit devices

> Adafruit produce a wide range of breakout and sensor boards, all of which are open source and accompanied by extensive documentation and tutorials.

* [Adafruit breakout boards](https://www.adafruit.com/category/42)
* [Adafruit sesnor boards](https://www.adafruit.com/category/35)

## Pin variants

Adafruit boards use a variety of interfaces, most of which are GPIO and/or I2C/SPI.

The UX2-GPIO provides 4 GPIO, 1 I2C, 1 SPI, 1 UART:

![UX2-GPIO](../../img/ux2-gpio.png)

The UX2-I2C provides 3 I2C, 1 SPI, 1 UART:

![UX2-I2C](../../img/ux2-i2c.png)

The UX2-ALT variant provides 2 GPIO, 2 I2C, 1 SPI, 1 UART:

![UX2-ALT](../../img/ux2-alt.png)

For devices that require I2S, use the UX2-GPIO pin variant and [configure the GPIOs for I2S](../I2S/README.md).

## Wiring

The wiring will depend on the devices you are connecting to, but generally:

* `3V3` usually connects to breakout `Vin` or `Vcc`
* `GND` connects to breakout `GND`
* Connect Async, I2C and SPI interfaces to breakout, where applicable
* For any remaining connections, use the GPIO (`Gx`) pins

## Host Considerations

TBC
