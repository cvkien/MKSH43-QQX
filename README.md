# Marlin-V2.X-MKS-H43
This reponsotory was downloaded from https://github.com/MarlinFirmware/Marlin/tree/bugfix-2.0.x, and added the support of MKS H43. This is for the convenience of users to clone and compile their own boards, especially before marlin officially incorporates the MKS H43 function. More infomation about MKS H43, please refer to https://github.com/makerbase-mks/MKS-H43.

## How to config
1. Using VSCode to open this Marlin source, and modify the motherboard type on the "platformio.ini" according to yours, just like:
```
default_envs = mks_robin_nano35
```
2. Config the MKS DWIN
- Open the "Configuration.h" file, find "DGUS_LCD_UI_MKS" and enable it,
- Open the "Configuration_adv.h" file, find "LCD_SERIAL_PORT", and configure the serial port number used to connect to H43. Please make sure that "LCD_SERIAL_PORT" should be different with the "SERIAL_PORT" in "Configuration.h", as "SERIAL_PORT" is used to communicate with the PC. And the baudrate should be set to 115200 by default.

## Setup you machine
1. Goto Settings>Auto Calibration, calibrate your delta
2. Goto Settings>Advance Configurations>Delta Configurations, check Delta Radius, the value should be 140.8, if the calibration changed the value, change back to 140.8.
3. Goto Settings>Level Bed
4. After level, remove leveling sensor, goto Home>Move, then move your Z to 0, then Disable Software Endstop, move carefully until it reach the correct z-offset, value should be around -16.8
5. Then remember the Z-position value, goto Settings>Probe Offset, change the Z-offset.
6. Then test first print, when lay first layer, goto Tune>Babysteps, then move the Z until the first layer is perfect, confirm babystep, z-offset will store automatically.
7. calibrate your flow and estep, try search google or youtube.
8. Done and enjoy your printer!
