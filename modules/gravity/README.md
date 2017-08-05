# Gravity Series (DFRobot)

> Gravity is an open source, plug and play toolkit with over 60 compatible modules.

* [Gravity Overview](https://www.dfrobot.com/gravity)
* [Gravity Modules](https://www.dfrobot.com/category-36.html)

## Pin variant

UX2-GPIO – four GPIO:

![UX2-GPIO](../../img/ux2-gpio.png)

## Wiring

There are two types of Gravity connector - analogue (blue) and digital (green), each using a 3 wire connector:

* `Gx` (GPIO) connects to the Gravity outer green or blue wire (Signal)
* `3V3` connects to the Gravity middle red wire (Voltage or Vcc)
* `GND` connects to the Gravity outer black wire (Ground)

## Host Considerations

Gravity hosts use color-coded male header as illustrated below:

![Gravity](./gravity.png)

As GPIO can be either analog or digital, you can connect up to 4 Gravity modules to a UX2-GPIO.