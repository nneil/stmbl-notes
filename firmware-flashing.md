Flashing STMBL firmware via USB DFU using ST DfuSe under Windows

The two boards of the STMBL each require their own firmware, which can be downloaded from https://github.com/rene-dev/stmbl/releases
The LV board uses `f3dfu.bin` and the HV board uses `hvf3.bin`
Once the two files have been downloaded you have several different ways of flashing them to the boards.
Flashing using USB DFU
THe usb port on each board is connect directly to the microcontroller. The permanent factory installed firmware implements a [USB DFU](http://wiki.openmoko.org/wiki/USB_DFU_-_The_USB_Device_Firmware_Upgrade_standard) device. This requires a specific driver under Windows.

[](Flashing STMBL firmware via USB DFU using ST DfuSe under Windows)
