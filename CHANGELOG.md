## Changes from mainbranch v7.1 to v7.1-1

### Changes applicable to both hardware versions:

* I2C read then write command is fixed
* Bug fix in the software delay function. Fix involves the use of a hardware based free running timer( TIMER1) that acts as the system tick reference. (#23)
* I2C clock stretching feature is now implemented (#90)


## Changes from 7.0 to 7.1:

### Bus Pirate v3 specific changes:

* The source tree can now be rebuilt for Bus Pirate v3 using MPLAB X.
* PC-AT keyboard mode is available for Bus Pirate v3 once more. (#19)
* PIC mode is available for Bus Pirate v3 once more. (#19)
* Firmware demos have been migrated to MPLAB X.
* Bootloader v4.5 has been migrated to MPLAB X.
* Experimental support for hardware I2C has been added. (#39)

### Bus Pirate v4 specific changes:

* Bootloader v1 has been migrated to MPLAB X.
* USB I/O now works when building the firmware using higher optimisation levels, working around a bug in recent xc16's code generator. (#11, #56)

### Changes applicable to both hardware versions:

* "pirate-loader" now needs to be built with CMake, to allow building on modern OSX and Windows versions.
* SUMP support is now an optional feature.
* SMPS support is now an optional feature.
* Modules configuration has been centralised into `Firmware/configuration.h`, allowing for more flexibility when creating custom images.
* Assigning a state to the AUX pin via BASIC scripts now works properly.
* Extra bus speeds are now available for SPI mode. (#25)
* Raw 2-wire mode now correctly honours LSB/MSB endianness settings. (#17)
* General refactoring and code cleanups have reduced both memory and code footprint when building without optimisations enabled.
* Firmware code sections do not overlap each other anymore. (#10)
* Delays are more accurate. (#23)
* 1-Wire now supports Overdrive mode. (#40)
* SPI macros to interactively tweak SPI parameters are now documented.

### Other:

* The message generation program has been turned into a Python script, to increase portability.
* Unused strings are stripped away by the linker whenever possible. (#60)
* Support for Bus Pirate v1A has been removed. (#6)
* Support for Bus Pirate v2, v2.5, and v2go is not going to be built in by default. (#6)
* Hardware schematics have been migrated to their own repo at [https://github.com/BusPirate/hardware](https://github.com/BusPirate/hardware) (#14)
* Documentation from Dangerous Prototypes' wiki has been converted into Markdown format and placed in the source repository. (#27)
* Firmware will now build by default with Optimisation level 1, this allows to fit more protocols on v3 boards in the default configuration.
