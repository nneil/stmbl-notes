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

- Click `OK` to choose `GENERATE`

![DFM](screenshots/DFM_Run.png)

- Choose `Multi Bin...`

![DFM](screenshots/DFM_Multi_Bin.png)

- Click `...` to open the file

![DFM](screenshots/DFM_Selection.png)

- Select the BIN file

![DFM](screenshots/DFM_Selection_File.png)

- Enter the correct address `0x08000000`

![DFM](screenshots/DFM_Address.png)

- Click `Add to list`
- Click `OK`

![DFM](screenshots/DFM_Add_to_list.png)

- Enter the version of the firmware as a 4 digit hex number
- Click `Generate...`

![DFM](screenshots/DFM_Version.png)

- Type the name of the DFU file to be created (you can optionally add the version number as part of the name)

![DFM](screenshots/DFM_DFU_File.png)

- Click `Save`

![DFM](screenshots/DFM_Success.png)

## Put the Board into DFU Mode
- Short the programming jumper on the board you wish to program (as pictured below)
- Apply power to that board.
- Once powered up the jumper can be removed. Windows Device Manager should show `STM Device in DFU Mode` (0483:DF11)

Shorting the programming jumper on the back of the low voltage board 
![Screenshot of `STMBL4.1_Low Voltage_Bootloader Jumper pads`](screenshots/STMBL4.1_LV_BL_J.png)	

Shorting the programming jumper on the top of the high voltage board 
![Screenshot of `STMBL4.1_High Voltage_Bootloader Jumper pads`](screenshots/STMBL4.1_HV_BL_J.png)	

Device manager showing board in DFU mode
![Device Manager](screenshots/Board_in_DFU_Mode.png)

# Flashing

- Start `DfuSeDemo`
- Under `Upgrade or Verify Action` click `Choose..`  

![Screenshot of `DfUse`](screenshots/DFUSE_Choose.png)

Select `f4.dfu` for the LV board or `f3.dfu` for the HV board

![Screenshot of `DfUse`](screenshots/DFUSE_Choose_File.png)

- Note the version displayed is what was entered earlier in `Dfu file manager`
- Note `File correctly loaded.` message
- Tick `Verify after download`
- Click `Upgrade` to flash the firmware to the board

![Screenshot of `DfUse`](screenshots/DFUSE_Upgrade.png)

- Accept the warning

![Screenshot of `DfUse`](screenshots/DFUSE_Confirm.png)


- Observe the `Erase Phase`, followed by the `Download Phase`

![Screenshot of `DfUse`](screenshots/DFUSE_Erasing.png)
![Screenshot of `DfUse`](screenshots/DFUSE_Downloading.png)

- Observe successful completion

![Screenshot of `DfUse`](screenshots/DFUSE_Success.png)

## Servoterm
Servoterm is a specialised terminal emulator that can be used to control the STMBL. It's a Chrome Extension.
The board must be in serial mode, the power must be cycled if it was previously in DFU mode for flashing.

![Screenshot of `DfUse`](screenshots/Board_in_Serial_Mode.png)

Start servoterm from the Chrome Apps menu, found on the bookmarks bar of a new tab, the URL is chrome://apps/
The command to check the firmware version is `about`
