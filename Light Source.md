To perform time-based measurements, you don't need a specialized light source. However, having a Light Unit attached to the Tester will greatly improve the comfort of using it. And having a calibrated light source will also increase the capabilities of the Tester.

## Light Unit #1

You can build your own Light Unit, connect it to the Tester's socket marked as a "Light Unit", and let Tester to turn it On and Off when you press "Start" or "Stop" while running tests.

The schematic is very simple. Basically, you can connect anything what can be controlled by a logic signal. Only resistor divider circuit is required to let the Tester know that Light Unit is connected.

![](https://github.com/srozum/film_camera_tester/blob/2ea1c309da684a7f24941bc87bdb02ca9bf8ade0/assets/schematics/light-unit-1.png)


## Light Unit #2

![](https://github.com/srozum/film_camera_tester/blob/67106fce64752653773c6c21b76f1bbce28fdd43/assets/images/light-unit-2-small-1.jpg)

"Light Unit #2" has special optic-electric design to satisfy requirements for standard light source used to test and adjust photometric light meters. It provides evenly illuminated surface, and it's brightness can be controlled within a wide range with good precision.

- EV values: 5..16 in two ranges for K12.5 and K14.03
- Calibration accuracy: 5%
- Unevennes of the screen luminance within 10%
- LED light source, analog of Cree XHP 70.2
- Color temperature varies within 2800K and 5000K
- Dimensions:
  - Screen size 80x80mm
  - Unit size 10x10cm and 18cm deep
- Power requirements: DC 12.5V 1.2A

For proper functioning, your Film Camera Tester should run firmware version [2.5](https://github.com/srozum/film_camera_tester/releases/tag/2.5) or higher.

Accuracy of the light output greatly depends on a quality of a power supply. It is recommended to use 12V 2A (or higher) power supply like "Mean Well" or similar, where output voltage can be finely adjusted within +/-1V.

Because of the Color Correction Factor of LED, old light meters like celenium meters, photoresistors or LDR, and some photodiodes read exactly 1 stop lower. More modern light meters, including digital cameras, read LED lights correctly.

> Big thanks to Peter Woodford who did numerous tests and helped to identify behaviour of various light meters.

Calibration was done using a Luminance meter with a probe placed directly against the screen. Below is a table of measured luminance (cd/m2) on a surface of the screen.


|EV   | K12.5 | K12.5 +1 | K14.03 | K14.03 +1 |
|---- | ----  | ----     | ----   | ----      |
|5    | 4     | 8        | 4.49   | 8.98      |
|6    | 8     | 16       | 8.98   | 17.96     |
|7    | 16    | 32       | 17.96  | 35.92     |
|8    | 32    | 64       | 35.92  | 71.8      |
|9    | 64    | 128      | 71.8   | 143.65    |
|10   | 128   | 256      | 143.65 | 287.3     |
|11   | 256   | 512      | 287.3  | 575       |
|12   | 512   | 1024     | 575    | 1149      |
|13   | 1024  | 2048     | 1149   | 2299      |
|14   | 2048  | 4090     | 2299   | 4595      |
|15   | 4090  | 8190     | 4595   | 9195      |
|16   | 8190  | 16390    | 9195   | 18390     |

> "+1" luminance values for older light meters

### Calibration

After assembling the Tester, Light Unit have to be calibrated by adjusting the voltage of a power source. You'll need a luminance meter or you can use any light meter with good resolution, but you have to know it's type and calibration constant.

- Adjust power supply voltage to exactly 12.5V. While adjusting the voltage be carefull to not exceed 13V or you can damage componets of the Tester!
- In settings select light mode level which corresponds to your light meter calibration contsant. If you are using luminance meter select K12.5.
- Set Tester in a "Light Source" mode, select light level 12 and turn it on.
- Place probe of a luminance meter directly against the screen at the center. Try to avoid moving it during calibration.
- Adjust voltage of power supply so the meter reads 512 cd/m^2 or slightly above. If you are using reflective light meter it should read 12EV.
- Once EV12 is calibrated correctly the rest of EV values should align properly. However, small variation in linearity is possible due differences in manufacturing tolerances of electronic components.

> If you don't have a proper light meter, adjust power supply voltage to exactly 12.5V and it should be good enough.

