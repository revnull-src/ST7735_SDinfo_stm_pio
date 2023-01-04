# ST7735_SDinfo_stm

This is a portable SD Card tester and CID analyzer that utilizes an STM32 development board (blue pill) and an ST7735 compatible LCD.
This fork has been updated for use in the PlatformIO development environment. Since the original project was built with an older version of the Arduino IDE, libraries, and toolchains, similar versions have been hardcoded in the platformio.ini.

## Features

- Uses a cheap STM32 development board and an ST7735 LCD with a built-in SD socket.
- Decodes CID, OCR, CSD, and status registers.
- Lists partition table and optional FAT filesystem parameters.
- **[Currently Broken]** CID unlock check based on Richard Burton's code: <https://richard.burtons.org/2016/07/01/changing-the-cid-on-an-sd-card/>
- Requires STM32 port of SdFat, Fast ST7735, and RRE Font libraries.
- Provided compiled binary ready to flash
- SD Card specs: <https://www.sdcard.org/downloads/pls/>

If you find this project useful please support the original author:

<https://www.paypal.me/cbm80amiga>

## Demonstration Videos

<https://youtu.be/s2bYx58kJ_U>

<https://youtu.be/ZAe61GZ-52Y>

More ST7735 and STM32 projects:

<https://www.youtube.com/watch?v=o3AqITHf0mo&list=PLxb1losWErZ6y6GombzvtwRZ2l7brPv1s>

## Connections

There are several versions of the ST7735/SD Card board, each with unique pinouts and names. The following table will attempt to provide a basic pin mapping from the LCD to the STM32. Please consult your LCD's documentation if you are unsure what to do.

**ST7735 LCD:**
|LCD Pin|STM32 Pin|
|--|--|
|LED|3.3V/5V|
|CLK/SCK|PA5/SCK|
|SCA/SDA/MOSI|PA7/MOSI|
|A0/RS/DC|PA1 or any digital|
|RESET|PA0 or any digital|
|CS|PA2 or any digital|
|GND|GND|
|VCC|3.3V/5V|

**SD Card:**
|SD Pin|STM32 Pin|
|--|--|
|SD_SCK|PA5|
|SD_MISO|PA6|
|SD_MOSI|PA7|
|SD_CS|PA4|

**Button:**
|Button Pin|STM32 Pin|
|---|---|
|#1|PB9|
|#2|GND|
