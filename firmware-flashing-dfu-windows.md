Flashing STMBL firmware via USB DFU using ST DfuSe under Windows
- Download `f3dfu.bin` and `hvf3.bin` from https://github.com/rene-dev/stmbl/releases
- Download `DfuSe Utility` from http://www.st.com/en/development-tools/stsw-stm32080.html 
note that that ST refer to it by serveal differeent names. This package contains the GUI utility as well as the required device driver.
- Power up the boards and connect the USB cable to the LV or HV board
- Start `DfuSe`

![Screenshot of `DfUse`](screenshots/DfuSe.png)

- Under `Upload Action` click `Choose..` and choose the `f3dfu.bin` for the LV board or `hvf3.bin` for the HV board. Accept the strange warning that appears.
- Click `Upload` to flash the firware to the board
- Repeat the process for the other board
