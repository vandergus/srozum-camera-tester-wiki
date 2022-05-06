To perform time-based measurements, you don't need a specialized light source. However, having a Light Unit attached to the Tester will greatly improve the comfort of using it. And having a calibrated light source will also increase the capabilities of the Tester.

##Light Unit #1##

You can build your own Light Unit, connect it to the Tester's socket marked as a "Light Unit", and let Tester to turn it On and Off when you press "Start" or "Stop" while running tests.

The schematic is very simple. Basically, you can connect anything what can be controlled by a logic signal. Only resistor divider circuit is required to let the Tester know that Light Unit is connected.

![](https://github.com/srozum/film_camera_tester/blob/2ea1c309da684a7f24941bc87bdb02ca9bf8ade0/assets/schematics/light-unit-1.png)


##Light Unit #2##

![](https://github.com/srozum/film_camera_tester/blob/67106fce64752653773c6c21b76f1bbce28fdd43/assets/images/light-unit-2-small-1.jpg)

"Light Unit #2" has special optic-electric design to satisfy requirements for standard light source used to test and adjust photometric light meters. It provides evenly illuminated surface, and it's brightness can be controlled within a wide range with good precision.

- EV values: 4..16 in two ranges for K12.5 and K14.03
- Calibration accuracy: 5%
- Unevennes of the screen luminance within 10%
- LED light source, analog of Cree XHP 70.2
- Color temperature varies within 2800K and 5000K
- Dimensions:
 - Screen size 80x80mm
 - Unit size 10x10cm and 18cm deep
- Power requirements: DC 12.5V 1.2A

For proper functioning, your Film Camera Tester should run firmware version [2.5](https://github.com/srozum/film_camera_tester/releases/tag/2.5).

Accuracy of the light output greatly depends on a quality of a power supply. It is recommneded to use 12V 2A (or higher) power supply like "Meanwell" or similar, where output voltage can be finely adjusted within +/-1V. When connected, adjust power supply voltage to exactly 12.5V, and make sure it stays the same whether Light Unit is on or off.

Calibration was done using a Luminance meter. Below is a table of measured luminance (cd/m2) on a surface of the screen.


|EV   | K12.5  | K14.03|
|---- | ----   | ----  |
|4    | 4      | 4.49  |
|5    | 8      | 8.98  |
|6    | 16     | 17.96 |
|7    | 32     | 35.92 |
|8    | 64     | 71.8  |
|9    | 128    | 143.65|
|10   | 256    | 287.3 |
|11   | 512    | 575   |
|12   | 1024   | 1149  |
|13   | 2048   | 2299  |
|14   | 4090   | 4595  |
|15   | 8190   | 9195  |
|16   | 16390  | 18390 |



> Because of the Color Correction Factor of LED, some light meters (mostly of modern electronic cameras) might read exactly 1 stop higher.
