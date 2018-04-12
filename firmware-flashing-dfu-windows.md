# STMBL firmware flashing under Windows via USB DFU using ST DfuSe
INCOMPLETE DO NOT USE - DRAFT - MAY BE INCORRECT
This documents the initial flashing of an "empty" board.
## Download
- Download `f4.bin` (for the LV board) and `f3.bin` (for the HV board) from https://github.com/rene-dev/stmbl/releases
- Download `DfuSe Utility` from http://www.st.com/en/development-tools/stsw-stm32080.html 
Note that ST refer to the utility by several different names, and that the use of English in the package is not perfect. This package contains:
- GUI utility flashing (`DfuSeDemo`)
- Utility to create DFU files (`Dfu file manager`)
- STM32 DFU device driver.
## Create DFU File from BIN file
The downloaded file needs to be converted from BIN to DFU. For each BIN file you must:

- Run `Dfu file manager` from the Windows Start Menu

- Choose `GENERATE`

![DFM](screenshots/DFM_Run.png)

- Choose `Multi Bin...`

![DFM](screenshots/DFM_Generation.png)

- Click `...` to open the file

![DFM](screenshots/DFM_Selection.png)

- Select the file

![DFM](screenshots/DFM_Selection_File.png)

- Enter the correct address `0x0800000`

![DFM](screenshots/DFM_Address.png)

- Click `Add to list`

![DFM](screenshots/DFM_Add_to_list.png)

- Enter the version of the firmware as a 4 digit hex number

![DFM](screenshots/DFM_Version.png)

- Type the name of the DFU file to be created (you can optionally add the version number as part of the name)

![DFM](screenshots/DFM_DFU_File.png)

- Click `Generate...`

![DFM](screenshots/DFM_Success.png)


Increment Version
## Put board into DFU Mode
- Short the programming jumper on the board you wish to program (as pictured below)
- Apply power to that board.
- Once powered up the jumper can be removed. Windows Device Manager should show "STM Device in DFU Mode" (0483:DF11)

Shorting the programming jumper on the back of the low voltage board 
![Screenshot of `STMBL4.1_Low Voltage_Bootloader Jumper pads`](screenshots/STMBL4.1_LV_BL_J.png)	

Shorting the programming jumper on the top of the high voltage board 
![Screenshot of `STMBL4.1_High Voltage_Bootloader Jumper pads`](screenshots/STMBL4.1_HV_BL_J.png)	

Device manager showing board in DFU mode
![Device Manager](screenshots/Board_in_DFU_Mode.png)

# Flashing

- Start `DfuSeDemo`

![Screenshot of `DfUse`](screenshots/DfuSe.png)

- Under `Upgrade or Verify Action` click `Choose..` and select `f4.dfu` for the LV board or `f3.dfu` for the HV board. Note the version displayed is what was entered earlier in `Dfu file manager`.
- Click `Ugrade` to flash the firmware to the board
- Observe the Erase Phase followed by the `Download Phase`
- Repeat the process for the other board
## Servoterm
Start servoterm from the Apps menu, found on the bookmarks bar of a new Chrome tab, the URL is chrome://apps/
Command to check version is `about`

