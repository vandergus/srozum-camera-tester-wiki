## Arduino Nano Compatible Shield Board

- Atmega328p microcontroller (Arduino compatible) with firmware Version 2.3 uploaded
- Shield PCB V2 Rev.2
- Header Pin Connector 15P F x2
- Active Buzzer 5V
- Capacitor 220µF 50V x2
- 9P F JST XH2.54 Connector
- 6P F JST XH2.54 Connector x3
- 2P F JST XH2.54 Connector
- 2P M JST XH2.54 Connector with wires attached
- Resistor 10K 0.125W x2

## LCD Unit

- LCD2004A with I2C interface board based on PCF8574T chip, which has default address 0x27
- 4P M JST XH2.54 Connector with wires attached
- Header Pin Connector 4P F

## Keypad Unit

- Keypad PCB V1 (vertical) or V2 (horizontal)
- Rotary Encoder 15mm
- Rotary Encoder Knob 20x13
- Push Button 12*12*7.3MM x4
- Push Button Cap - Black x2
- Push Button Cap - Red
- Push Button Cap - Yellow
- 9P M JST XH2.54 Connector with wires attached

## Sensor Socker

- 6P M JST XH2.54 Connector with wires attached
- Socket GX16x6 Female
- Heat Shrink Tubing 3mmx30mm x3

## Sensor #1 (Diagonal Sensor)

- Sensor PCB
  - V1 has 32x22mm spacing between outmost phodotiodes
  - V2 has 32x20mm spacing
- Light To Logic converter Photo IC (photodiode with integrated amplifier and schmitt trigger) x3
  - ![Laser Sensor](https://github.com/srozum/film_camera_tester/blob/ff70038ed548a19df9affb2cfab41a057fedca4c/assets/images/laser%20sensor%20module.jpeg)
  - [SIC553-04](https://github.com/srozum/film_camera_tester/blob/ff70038ed548a19df9affb2cfab41a057fedca4c/assets/datasheets/SIC553-04.pdf) made by Kodenshi Corp., this is what originally was used in those "Laser Sensor" modules.
  - [PIC0903SL](https://github.com/srozum/film_camera_tester/blob/25081f90891dfd4f507b88cfab1606393add9a17/assets/datasheets/PIC0903SL-KODENSHI.pdf) is a new version of SIC553-04 also made by Kodenshi.
  - However, if your Tester registers dark time instead of light time, it means that you've got a module version equipped with [PIC0103SL](https://github.com/srozum/film_camera_tester/blob/25081f90891dfd4f507b88cfab1606393add9a17/assets/datasheets/PIC0103SL-KODENSHI.pdf). It uses same schematics, and product photos are the same, but output signal is reversed. In such case simply use Firmware v2.9.1 were sensor readings inverted.
- 3D Printed Enclosure parts (face plate, body and a lid)
- 2x6mm Tapping Screw x2
- Zip Tie
- Foam Pad 5x5mm x3
- 1/4 20 UNC(IFC) Threaded Insert
- Socket GX16x6 Male
- 24AWG 6 Core UL2464 Cable 0.8m
- Heat Shrink Tubing 6mmx30mm

## Sensor #2 (Simple Sensor)

- Sensor PCB V2
- Light To Logic converter Photo IC (photodiode with integrated amplifier and schmitt trigger) PIC0903SL (SIC553-04 old part name) or PIC0103SL
- 3D Printed Enclosure parts (body and a lid)
- 3D Printed Medium Format Adapter
- Socket GX16x6 Male
- 2x6mm Tapping Screw x2
- Zip Tie
- 24AWG 4 Core UL2464 Cable 0.8m
- Heat Shrink Tubing 6mmx30mm

## Sensor #6 (Exposure Sensor)

- Sensor PCB V4
- Photodiode TSL237
  - Light To Frequency converter.
  - [Datasheet](https://github.com/srozum/film_camera_tester/blob/ff70038ed548a19df9affb2cfab41a057fedca4c/assets/datasheets/TSL237.pdf)
- 3D Printed Enclosure parts (face plate, body and a lid)
- 3D Printed Medium Format Adapter
- Socket GX16x6 Male
- 2x6mm Tapping Screw x2
- Foam Pad 10x10mm
- Zip Tie
- 24AWG 4 Core UL2464 Cable 0.8m
- Heat Shrink Tubing 6mmx30mm

## Sensor #7 (Flash Sync Sensor)

- Cable with PC Connector
- Socket GX16x6 Male
- Resistor 10K 0.125W
- Resistor 39K (closest standard to it) 0.125W
- Heat Shrink Tubing 6mmx30mm

## Light Unit #2 Rev.4

- Light Unit #2 Control Board Rev.3
  - PCB / Light Unit #2 Rev.3
  - LD24AJTA (based on PT4115) LED Driver.
    - Rcs 0.91 Ohm
    - [Datasheet](https://github.com/srozum/film_camera_tester/blob/ff70038ed548a19df9affb2cfab41a057fedca4c/assets/datasheets/PT4115E.pdf)
  - Header Pin Connector 6P M as LED driver mounts
  - 2N2222A TO-92 NPN Transistor
  - Diode 1N4001
  - Resistor 2K 0.125W
  - Resistor 2.2K 0.125W
  - Resistor 3.9K 0.125W
  - Resistor 4.7K 0.125W
  - Capacitor 220µF 25V
  - Capacitor 330µF 25V
  - 2P F JST XH2.54 x2
  - 2P M JST XH2.54 w/ 26AWG Wire
  - 2P F JST PH2.0
  - 6P M JST XH2.54 w/ 26AWG Wire
- 3D Printed Front Panel Frame
- 3D Printed Reflector Mount Frame
- 3D Printed Reflector
- 3D Printed LED Mount
- Diffuser "Silky White" 88x88 6mm thick
  - acrylic sheet, glossy on one side (facing inwards), matte on other side (facing outwards)
- Acrylic Fresnel Lens diameter 50mm, focal length 40mm
- Epileds XHP7070.2 12V 3000K LED
  - chinese analog of Cree XHP70.2
- 10W Heatsink With Fan
- 2P M JST PH2.0 w/ 22AWG 15cm Wire
- M3x20 Hex Screw Black x4
- M3x65 Threaded Rod x4
- M3 Nut x12
- M3x6 1mm Nylon Washer x8
- Nylon Spacer M3x15 x4








