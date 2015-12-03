
# OSHChip_CMSIS_DAP_V1.0 Programmer and Debugger


<img src="OSHChip_CMSIS_DAP_V1.0.jpg" alt="OSHChip_CMSIS_DAP_V1.0" width="600" align="middle">


## Description

OSHChip_CMSIS_DAP_V1.0 connects to a host computer over a USB interface
and provides 3 services:

* USB to CMSIS-DAP programming with a SWD connection to the target.
Use this with the Keil IDE. This should be able to program any
processor that the Keil IDE supports (there are hundreds) that can be
programmed via SWD. There is also support for debugging with GCC's GDB
debugger, via pyOCD

* USB MSD (Mass Storage Device), shows up like a USB memory
stick/drive, named MBED. You can drag and drop .HEX files to this
drive, and it will convert the file to the appropriate SWD pin
wiggling and program a nRF51822 which is the processor on OSHChip_V1.0

* USB to virtual COM port. The board provides serial I/O at LVTTL (0
to 3.3V) levels on the 2 pin header on the end of the board. These can
be connected to anywhere in your system that has async serial I/O, so
no specific pins on OSHChip_V1.0 are required. I haven't tested it
yet, but it should work from 9600 to 115200 BAUD.

## OSHChip_CMSIS_DAP_V1.0 Design Files

This repository contains the design files for **OSHChip_CMSIS_DAP_V1.0**

The PCB design files are in the directory *Design_Files* and were
created with Altium Designer Release 10

Since you may not have access to Altium Designer, I have also
included all the Gerber files and the Excelon drill file in the
directory *Gerbers_and_Drill_Files*.

In the *Other_Files* directory, you will find the following:
* OSHChip_CMSIS-DAP_V1.0___Schematic.PDF
* OSHChip_CMSIS-DAP_V1.0___PCB_Prints.PDF
* OSHChip_CMSIS-DAP_V1.0___Assembly_Drawings.PDF
* OSHChip_CMSIS-DAP_V1.0___Bill_of_Materials.xls
* OSHChip_CMSIS-DAP_V1.0___Bill_of_Materials.PDF

## OSHChip_CMSIS_DAP_V1.0 design Parent

The bulk of this project is derived from the mbed HDK and SDK.

The original design files are in Eagle format. The schematics have
been re-drawn in Altium, and some of the components were replaced with
alternatives that were more readily available. The PCB layout is new,
but for obvious reasons, it is also quite similar to the mbed PCB
design that is in Eagle format.

OSHChip_CMSIS_DAP_V1.0 uses USB mini-B rather than USB micro-B
connector (probably a mistake. I'll change it on the next version to
micro-B) and most importantly, OSHChip_CMSIS_DAP_V1.0 makes the USB-
to-Serial interface available.

The serial input and output pins are available at the same end of the
PCB as the SWD connector. Conveniently, if a jumper is installed on
this connector, the serial link is looped back, allowing easy testing
of the setup of terminal programs on the host computer.

## The Hardware parent

This design is derived from mbed HDK (Hardware Development Kit)

An overview is provided here <a href="https://developer.mbed.org/handbook/mbed-HDK" target="_blank">mbed HDK</a>

The Hardware files are here <a href="https://developer.mbed.org/teams/mbed/code/mbed-HDK" target="_blank">mbed HDK Design Files</a>

## The Firmware parent

The Firmware is described here <a href="https://developer.mbed.org/handbook/cmsis-dap-interface-firmware" target="_blank">mbed HDK Firmware</a>

The firmware described can be used with several different microprocessors
which can be seen here <a href="https://github.com/mbedmicro/CMSIS-DAP/tree/master/interface/mdk" target="_blank">Microprocessors</a>

OSHChip_CMSIS_DAP_V1.0 uses the NXP LPC11U35 microprocessor.
The above firmware is quite dated and does not describe the nRF51822 target CPU
that is used in OSHChip_V1.0. A branch of this firmware with support
for nRF51822 has been developed by Yihui Xiong of Seeed Studio.
This version of the firmware is also used by OSHChip_CMSIS_DAP_V1.0.

It is here <a href="https://github.com/xiongyihui/CMSIS-DAP" target="_blank">Firmware Supporting nRF51822</a>

For the firmware, only very minor cosmetic changes were made
to acknowledge its origin.

## License: Apache 2.0

The License for the mbed files is Apache 2.0 and can be found in
the repositories linked above.

The OSHChip_CMSIS_DAP_V1.0 files and changes are Licensed with
the same Apache 2.0 license.

Copyright 2015 OSHChip (only for the Altium version of the design files)

Licensed under the Apache License, Version 2.0 (the "License"); <br>
you may not use this file except in compliance with the License.

You may obtain a copy of the License at <a href="http://www.apache.org/licenses/LICENSE-2.0" target="_blank">Apache LICENSE-2.0</a>

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License


