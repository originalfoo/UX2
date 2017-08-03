# UX2: Universal Extension Bus

UX2 is an open source board-to-board communication bus which supports [1-Wire](https://www.wikiwand.com/en/1-Wire), [Interrupt](https://www.wikiwand.com/en/Interrupt), [Async](https://www.wikiwand.com/en/Asynchronous_serial_communication), [I2C](https://www.wikiwand.com/en/I%C2%B2C), [SPI](https://www.wikiwand.com/en/Serial_Peripheral_Interface_Bus) and [Sound-Wire](https://www.mipi.org/specifications/soundwire) protocols.

## Quick Reference

There are two variants: UX2 (fully compatible with [UEXT](https://www.wikiwand.com/en/UEXT)), and Micro UX2 (device-dependent implementation):

![UX2 Pinout](./UX2_Pinout.png)

### Pins

* `1W` – 1-Wire data pin, to be used in conjunction with the `GND` pin
    * If 1-Wire is not required, this pin can be repurposed as a [GPIO](https://www.wikiwand.com/en/General-purpose_input/output)
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

The larger UX2 Bus is an extension to, and thus fully compatible with, a UEXT Bus; 10-pin UEXT connectors fit in the middle (the grey section shown on the pinout diagram above) of the 12-pin UX2 Bus socket, leaving the additional UX2 pins (1-Wire, Interrupt, Sound-Wire) exposed either side of the UEXT connector.

The host/master board must ensure the UEXT pins adhere to the [UEXT specifications](https://www.olimex.com/Products/Modules/UEXT/resources/UEXT_rev_B.pdf) so that existing UEXT modules ([like these](https://www.olimex.com/Products/Modules/)) can be used.

### Micro UX2

TBC

## License

See [License](./LICENSE).
