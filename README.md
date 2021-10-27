# Notes on the STMBL Boards
- [Firmware Flashing](firmware-flashing.md)

# STMBL Virtual ComPort
0483:5740

THis VID:PID is listed as belonging to STM32F407
0483:5740 STMF3 Comport

Replugging the USB connector several times is necessary before Servoterm is able to connect.

# Blink Error Codes

1. Command Error. Common during setup. Only really relevant to smart-serial
2. Motor Feedback Error
3. Commutation Feedback Error
4. Joint Feedback Error
5. Position Error
6 Saturation Error
7 Motor temperature high
8 HV Board serial CRC Error
9 HV Board comms Timeout Error
10 HV Board over-temperature
11 HV Voltage out of range
12 HV Board Fault
13 HV current offset fault
14 HV Overcurrent RMS
15 HV Overcurrent Peak
16 HV Overcurrent HW
