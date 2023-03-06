# Notes on the STMBL Boards
- [Firmware Flashing](firmware-flashing.md)

# Servoterm

Launch from <chrome://apps/>

# STMBL Virtual ComPort

<https://www.st.com/en/development-tools/stsw-stm32102.html>

Temporary email for sign-up https://temp-mail.org/

0483:5740

THis VID:PID is listed as belonging to STM32F407
0483:5740 STMF3 Comport

Replugging the USB connector several times is necessary before Servoterm is able to connect.

# Commands

```
hv0.pos = sim0.vel
```
```
hv0.d_cmd = 0.5
```
```
hv0.en = 1
```

Speed controlled by

```
sim0.freq = 5
```


# Blink Error Codes
```
1 Command Error. Common during setup. Only really relevant to smart-serial
2 Motor Feedback Error
3 Commutation Feedback Error
4 Joint Feedback Error
5 Position Error
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
```
