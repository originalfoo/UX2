# UX2: Universal Extension Bus

UX2 is an open source board-to-board communication bus which supports:

* [1-Wire](https://www.wikiwand.com/en/1-Wire)
* [Interrupt](https://www.wikiwand.com/en/Interrupt) – wake master/host MCU on slave/module interrupt
* [Async](https://www.wikiwand.com/en/Asynchronous_serial_communication)
* [I2C](https://www.wikiwand.com/en/I%C2%B2C)
* [SPI](https://www.wikiwand.com/en/Serial_Peripheral_Interface_Bus)
* [Sound-Wire](https://www.mipi.org/specifications/soundwire)

In addition, some pins can be repurposed as [GPIO](https://www.wikiwand.com/en/General-purpose_input/output) or an additional I2C (to avoid using [I2C address changers](http://hackaday.com/2017/02/17/ltc4316-is-the-i2c-babelfish/)).

## Quick Reference

There are two variants: UX2 (fully compatible with [UEXT](https://www.wikiwand.com/en/UEXT)), and Micro UX2 (device-dependent implementation):

![UX2 Pinout](./UX2_Pinout.png)

### Pins

* `1W` – 1-Wire data pin, to be used in conjunction with the `GND` pin
    * If 1-Wire is not required, this pin can be repurposed as a GPIO
* `INT` – Interrupt, allowing sensors to trigger an interrupt on host/master MCU
    * If interrupts are not required, this pin can be repurposed as a GPIO
* `GND` – Ground pin (0V)
* `3V3` – 3.3V power supply; max 100mA draw (UX2, UEXT) or implementation-dependent (Micro UX2)
* `RXD`, `TXD` – Async interface
* `SDA`, `SCL` – I2C interface
* `MOSI`, `MISO`, `SSEL`, `SCK` - SPI interface
    * `SSEL` = `SS` (Slave Select)
* `SWD`, `SWC` – Sound-Wire interface
    * If Sound-Wire is not required, these pins can be repurposed as an additional I2C interface

If pins are repurposed, it should be made clear to end-users that this is the case – ideally with labelling on the PCB silk screen.

### UX2, UEXT

The larger UX2 bus is an extension to, and thus fully compatible with, a UEXT bus; 10-pin UEXT connectors fit in the middle (the grey section shown on the pinout diagram above) of the 14-pin UX2 socket, leaving the additional UX2 pins (1-Wire, Interrupt, Sound-Wire) exposed either side of the UEXT connector.

The host/master board must ensure the UEXT pins adhere to the [UEXT specifications](https://www.olimex.com/Products/Modules/UEXT/resources/UEXT_rev_B.pdf) so that existing UEXT modules ([like these](https://www.olimex.com/Products/Modules/)) can be used.

### Micro UX2

The Micro UX2 bus is a variant that has all the same pins as UX2, but with some notable differences:

* It's connector-agnostic 
    * The host/master PCB has complete freedom to use any type of connector; useful when there's space constraints or other factors that would make the normal UX2 connector infeasible
    * For example, you could use [pin header](https://www.wikiwand.com/en/Pin_header) and [jumper wires](https://www.wikiwand.com/en/Jump_wire), or [ZIF connectors](https://www.wikiwand.com/en/Zero_insertion_force) and [flexible flat cable](https://www.wikiwand.com/en/Flexible_flat_cable)...
* All pins, except `GND` and `3V3`, are disabled by default
    * Saves power and complexity in host/master circuits that use energy harvesting or have limited MCU capacity
    * Features are enabled on an as-needed basis, either via jumpers, configurations or software; you decide how that works
* The max current on the `3V3` pin is implementation-dependent
    * Specification is defined by what the host/master can provide rather than what the module/slave expects
    * Particularly useful for host/master circuits that use energy harvesting or some other limited form of power

## Background

I wanted to facilitate end-user modding of a sensor project I was working on, and was originally planning to use UEXT bus – until it became apparent that some extra features were required (interrupt and sound-wire), hence the birth of UX1.

UX1 initially had the 4 additional pins to the right of the SPI interface, with one of the pins being unused. While searching for suitable sockets it quickly became apparent that this configuration wasn't compatible with UEXT modules - unless the IDC sheath was removed from the socket (at which point cable could be put in wrong way round = doom). To rectify this, the unused and interrupt pins were moved over to the left allowing compatibility with 10-pin UEXT plugs and also 14-pin plugs for what is now known as UX2.

During prototyping, I realised the 14-pin IDC connectors are bulky af, so Micro UX2 was born. In addition, with the circuit relying on energy harvesting, which also mandated lower power and smaller capacity MCU, the specs for Micro UX2 were changed to have everything disabled by default.

Finally, there were a few sensors that used 1-wire so that last unused pin suddenly found it's vocation - the fact that it was seated right next to `GND` is surely proof that this was its destiny. As many mods won't require 1-wire, sound-wire or even interrupts in many cases, it was decided to allow some limited pin repurposing to GPIO (for 1-wire and interrupt pins) and I2C (for the sound-wire pins).

I decided to document it all while it was all still fresh in my mind, hence this github project! If you find it useful or incorporate it in one of your projects, please let me know (via issues tab above) :)

## License

See [License](./LICENSE).
