# UX2: Universal Extension Bus

UX2 is an open source board-to-board communication bus which supports [1-Wire](https://www.wikiwand.com/en/1-Wire), [Interrupt](https://www.wikiwand.com/en/Interrupt), [Async](https://www.wikiwand.com/en/Asynchronous_serial_communication), [I2C](https://www.wikiwand.com/en/I%C2%B2C), [SPI](https://www.wikiwand.com/en/Serial_Peripheral_Interface_Bus) and [Sound-Wire](https://www.mipi.org/specifications/soundwire) protocols.

> **Note:**  
> UX2 is a derivative of, and extension to, the [UEXT Bus](https://www.olimex.com/Products/Modules/UEXT/resources/UEXT_rev_B.pdf); it is not associated with, or endorsed by, Olimex (creators of the orginal UEXT specification).

## The Pinout

There are two variants, UX2 (fully compatible with UEXT) and Micro UX2 (device-dependent implementation), as shown below:

![UX2 Pinout](./UX2_Pinout.png)

### UX2, UEXT

The UX2 Bus is designed to be fully compatible with the UEXT Bus; all existing UEXT modules ([like these](https://www.olimex.com/Products/Modules/)) and their connectors can be used with this variant of the UX2 Bus.

Standard 10-pin UEXT connectors fit in the middle (the grey section shown on the pinout diagram above) of the 12-pin UX2 Bus socket, leaving the UX2-specific pins on either side exposed.

> **Note:**  
> The host/master board must ensure UEXT pins (Power, Async, I2C and SPI) adhere to the [UEXT specifications](https://www.olimex.com/Products/Modules/UEXT/resources/UEXT_rev_B.pdf).

The additional pins aded by UX2 are:

* Left: [1-Wire](https://www.wikiwand.com/en/1-Wire) and [Interrupt](https://www.wikiwand.com/en/Interrupt)
    * Either pin can be repurposed as GPIO
* Right: [Sound-Wire](https://www.mipi.org/specifications/soundwire)
    * If Sound-Wire is not used, the pins can be repurposed as an additional I2C

### Micro UX2

TBC

## License

See [License](./LICENSE).
