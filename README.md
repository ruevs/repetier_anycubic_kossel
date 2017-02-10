Repetier Firmware Configured for the [Anycubic Kossel Linear][anycubic] Delta 3D Printer
==========

This repository contains the [Repetier-Firmware][] [version 0.92.9][ver]
configured for the [Anycubic Kossel Linear][anycubic] delta 3D printer.

This is a full assembly video and review of the printer:

[![Anycubic assembly video](http://img.youtube.com/vi/Bd7Z4JIQjQM/0.jpg)](http://www.youtube.com/watch?v=Bd7Z4JIQjQM)

[anycubic]: https://s.click.aliexpress.com/e/imu7Y7i
[Repetier-Firmware]: https://www.repetier.com/documentation/repetier-firmware/
[ver]: https://www.repetier.com/firmware/v092/

Installation
------------

Follow the instructions in the [README.txt](README.txt) to compile and install
the firmware on the TriGorilla board that the Anycubic printer uses.

Calibration and configuration
------------

The printer configuration is done in the Configuration.h file.
Every time you change this file you need to compile and flash
the firmware by following the instructions above.

To calibrate the printer follow [these instructions on Calibrating a Delta 3D Printer][minow].
Instead of the RepetierHost scripts suggested there use the ones below.
They are with a diameter of 160mm and leave the head 5mm above the
build plate allowing you to manually move it down to avoid crashing.

Script 1: Center of bed

    G28
    G0 Z5 F3500

Script 2: Alpha tower

    G28
    G0 Z5 X-69.28 Y-40 F3500

Script 3: Beta tower

    G28
    G0 Z5 X69.28 Y-40 F3500

Script 4: Gamma tower

    G28
    G0 Z5 X0 Y80 F3500

The parameters you will need to change are:

### Printer Height

```C
#define Z_MAX_LENGTH 297.9
```

### Diagonal rod lengrh

It is unlikely you will have to change this setting. The rods seem to be made
very precisely.

```C
#define DELTA_DIAGONAL_ROD 217 // mm
```

### Printer radius

```C
#define ROD_RADIUS 98.5
#define PRINTER_RADIUS 98.5
```

[minow]: http://minow.blogspot.bg/index.html#4918805519571907051

License
-------

Same as the original Repetier-Firmware.