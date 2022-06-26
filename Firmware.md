I continue to work on new features and improvements received thanks to your feedback, and new versions of a Firmware are published time from time.

You don't have to buy new Nano board every time new version of firmware is published, instead you could upgrade your Tester yourself by simply uploading new version into your board.

Uploading new firmware to Arduino Nano board is similar to uploading any sketch, but there is a trick. The thing is, the firmware takes so much space (v2.5 uses 31380 bytes of flash memory, for example) that it doesn't fit into regular Nano board.

What I mean by "regular" Nano?

For some unknown reason Nano boards configured in avrdude utility and in all IDEs like "Arduino IDE" or "Platform IO" in such way that upload maximum size specified as 30720 bytes, unlike for Uno is 32256 bytes. While same Atmega 328P chip used in both Nano and Uno, thus must have same characteristics, and they are the same.

Another common issue is that there are tons of Arduino Nano compatible boards available, but lots of them have so called "old bootloader" installed. Old bootloader takes more space, thus leaving less space for your program.

First issue is very easy to overcome. You simply tell the programmer that the board is Arduino Uno and proceed with updating firmware via USB cable as usual.

The second issue only could be fixed by using the ISP Programmer (or another arduino board as an ISP Programmer) to set the fuses and/or disable bootloader, and to upload the firmware. Some wiring of two boards together is required.

[Here](https://github.com/srozum/film_camera_tester/releases) you can find all released versions started from v2.3 which came with first Kit released as a product.

- **firmware.hex** - is a firmware pre-compiled for Arduino Nano boards
- **settings.hex** - is a dump of EEPROM memory with default settings.


###How to upload a firmware using another Arduino board as ISP programmer:

Please, read that article on official website [https://docs.arduino.cc/built-in-examples/arduino-isp/ArduinoISP](https://docs.arduino.cc/built-in-examples/arduino-isp/ArduinoISP)

Once you have prepared your Arduino ISP programmer and connected both boards together, run following commands from a folder where firmware files are downloaded.

PATH TO AVRDUDE - you can find it in a log window of Arduino IDE when you upload any sketch. Verbose log output should be enabled in preferrences.

COM PORT - port name where is you Arduino ISP programmer connected.

```
// erase and unlock the board
C:\<PATH TO AVRDUDE>\avrdude.conf -cavrisp -patmega328p -P<COM PORT> -b19200 -e -Ulock:w:0x3F:m

// setting bootloader fuses
C:\<PATH TO AVRDUDE>\avrdude.conf -cavrisp -patmega328p -P<COM PORT> -b19200 -D -Ulfuse:w:0xFF:m -Uhfuse:w:0xD7:m -Uefuse:w:0xFF:m

// uploading firmware and settings
C:\<PATH TO AVRDUDE>\avrdude.conf -cavrisp -patmega328p -P<COM PORT> -b19200 -D -Uflash:w:firmware.hex:i -Ueeprom:w:settings.hex:i

```


###How to upload a firmware using USBasp programmer:

```
// erase and unlock the board
avrdude -p atmega328p -c usbasp -P usb -e -U lock:w:0x3F:m

// setting bootloader fuses
avrdude -p atmega328p -c usbasp -P usb -D -U lfuse:w:0xFF:m -U hfuse:w:0xD7:m -U efuse:w:0xFF:m

// uploading firmware and settings
avrdude -p atmega328p -c usbasp -P usb  -D -U flash:w:firmware.hex:i -U eeprom:w:settings.hex:i
```

> **Remove Nano board from a Tester shield board during programming**



