This is Operation Manual for the Film Camera Tester running on Firmware **v2.7**. It has following test modes implemented:

- [Simple Shutters](#simple-shutters)
- [Focal Vertical](#focal-vertical--horizontal)
- [Focal Horizontal](#focal-vertical--horizontal)
- [Light Source](#light-source)
- [Average Series](#average-series)
- [Flash Sync Simple](#flash-sync-simple)
- [Flash Sync Focal](#flash-sync-focal)
- [Leaf Efficiency](#leaf-efficiency)

## Selecting a Mode

To select the Test Mode press the "Mode" button. Using a rotary encoder knob select which mode you want to run, and confirm your selection by pressing the knob.

Then, depending on the selected Mode and type of camera you are testing, connect a required sensor. Most of the time you'll use Sensor #1.

> **Although Tester supports sensors hot-swap, it is recommended to power off the Tester when connecting or disconnecting sensors**

When the correct sensor is connected,  and the Tester is ready to take measurements, you'll see "Press Start" on the screen. Otherwise, it will tell "Not Ready".

![](https://github.com/srozum/film_camera_tester/blob/0dc2f6d4f6b30f7b3b05398507d5e208c369ef96/assets/screenshots/screen-1.jpg)

The first row of the screen is a Status Bar. It tells you what sensors are connected to the Sockets A and B, the short name of selected Test Mode, and on a righthand of a line, there is an indicator of a selector for a primary setting of the Mode.


## Settings Menu

The Camera Tester has a Settings Menu for the items,  which are stored in EEPROM memory.

![](https://github.com/srozum/film_camera_tester/blob/0dc2f6d4f6b30f7b3b05398507d5e208c369ef96/assets/screenshots/screen-14.jpg)

**K Value** lets you select value of calibration constant K between 12.5 and 14.03. It switches Light Source output according to calibration tables.

**Frame Width** sets the target distance used to present curtains travel times. Curtains travel time can be presented as it was measured at a distance between far-most openings of a Sensor, or re-calculated over distance whichever is specified in service manual for a tested camera.

For example, the service manual for a Pentax K1000 says that the edge-to-edge travel time should be 14ms, or 13.3ms over the distance of 34mm, or 12.5ms over the distance of 32mm. But more common to see travel times specified as edge-to-edge. Since the horizontal distance between the far most photodiodes of a Sensor #1 is 32mm,  it is required to do some simple math to find out the travel time over the target distance vs the sensor's space. By setting the "Frame Width", results of focal plane shutter Test Modes will be automatically re-calculated for a set distance.

> The Tester automatically detects connected Sensor and thus knows what is a distance between photodiodes.

**Frame Height** similar to "Frame Width" but applying to focal plane shutters with vertical curtains travel direction.

**Speeds Range** lets you select between three sets of standard shutter speeds, depending on what camera you are testing - "New" (with speeds marked as 1/60, 1/125, etc.), "Old" (with speeds like 1/50, 1/100) or "Log" (with speeds like 1/128, 1/512).

- "New" range goes from 8s speed to 1/8000.
- "Old" range goes from 1s to 1/1000.
- "Log" range goes from 8s speed to 1/8000. Speeds are power of 2, for testing electronic cameras controlled by MCU.

**Test Series** sets the number of how many tests should be taken in average measuring modes before calculating and displaying the summary results.

- Choises are 3, 5, 10, or 20 tests in a series.

**Sound On/Off** enables or disables buzzer sounds.

To change settings in Settings Menu press the "Menu" button. Using a rotary encoder knob select which setting you want to edit and push the knob. Blinking symbol will appear next to the value, and you can change it by rotating a retary encoder knob. Pressing it again will store the selected value in a memory. To exit the Settings Menu, scroll down to the end of a list and select "Exit menu" item.

## Taking Measurements

Open the camera back and place the Sensor into a frame opening. For the cameras with focal-plane shutters, the orientation of a Sensor doesn't matter since the Tester automatically detects the direction of the curtains.

> Sensor #1 has a thread mount on its back in case you want to build a rig for holding it in an upright position.

> Sensor #2 has a "+" symbol on its back to help position it in a center of a frame in case of testing half-frame cameras.

For time-based tests, when testing cameras with a detachable lens it is recommended to remove the lens, otherwise set the aperture wide open.

Turn on the Light Source, unless it is a Light Unit controlled by the Tester, and place camera in front of it approximately 5-10cm away.

For light integrating tests, set lens at infinity (also remove any filters if present), and place camera directly against the Light Unit screen so that it covers the whole field of view of a lens and a light meter, in case of point-and-shoot type of camera.

When ready, press the "Start" button. At this moment the Tester should say "Running..." which means it is waiting for a shutter to be fired. Fire the shutter and if the test was successful you'll hear the "beep" and results will be printed on a screen immediately.

In all modes, except "Average Series", once the first test was taken and results were printed, you will no see "Running...", instead continue taking tests and fresh results will be displayed on a screen.

To change the Test Mode or Settings, press "Stop". Because during the Test all other controls are disabled.


## Simple Shutters

This basic mode allows you to quickly test cameras with shutters of different types at various speeds, as well as to get the efficiency interpolation for leaf shutters of size #00 and #0 (17-24mm aperture). I've collected efficiency data of various recently serviced shutters, like Prontor, Compur, Synchro-Compur, Seikosha, Copal, etc. This data is used to build realistic "efficiency curve", and to interpolate effective speed of the shutter in test.

In this mode Tester continuously measures exposure time, calculates effective speed and exposure error between effective and target speed. The target speed is either detected automatically as the nearest standard speed when the selector is set to "Auto", or the selected value is used.

Either of the Sensors #1, #2 or #3 can be used in this mode since only the center photosensor is utilized.

On screenshots below you can see measurements results of a Yashica Lynx-5000 shutter set at 1/500 and 1/1000 respectively. Yashica Lynx-5000 one of the few cameras which shutter has reinforced blades and able to reach speeds as high as 1/1000, with open/close time as fast as 0.7ms. As you can see, tester does a good job by estimating effective speed based on a time measured at the center of a frame. However, it's up to you how you interpret the results.


![](https://github.com/srozum/film_camera_tester/blob/fe5e2ac161eaef862774993a3b3540340639f97e/assets/screenshots/screen-22.jpg)

![](https://github.com/srozum/film_camera_tester/blob/fe5e2ac161eaef862774993a3b3540340639f97e/assets/screenshots/screen-23.jpg)

Results displayed on a screen:

- **"T"** - measured exposure time. Automatically formatted in s/ms/µs.
- **"S"** - measured shutter speed (time presented in a form "one over").
- **"Eff"** - shutter efficiency calculated using logarithmic interpolation and "effcicency curve" data.
- **"S"** - effective shutter speed calculated based on measured time and estimated efficiency.
- **"Er"** - calculated exposure error between measured and target speed. The target speed is either detected automatically as the nearest to effective speed, or the selected value is used.

When testing simple or leaf shutters the measured exposure time at the center of a frame is not an actual (or effective) speed. Especially it's applies for speeds above 1/60. For example, service manual for Compur shutters says that the nominal time measured on axis (at the center of a frame) for speed 1/125 should be 8.57ms instead of 10ms, or 2.7ms instead of 2ms for speed 1/500. Thus, some beginners repair people (used to be me) will try to get exact 1/250 speed by bending springs and levers until they damage the shutter unit.

> More about measuring efficiency you can read below in "Leaf Efficiency" mode description.

> Some old cameras have maximum aperture of f/4 of smaller. This, in combination with a big distance between lens and a focal plane where the sensor is placed, may cause problems during the tests. In this case, try to use powerfull flashlight instead of a built-in Light Unit.


## Focal Vertical / Horizontal

In this mode, using Sensor #1, you can test cameras with focal plane shutters, and get detailed results about exposure times at three points of a frame, opening and closing curtains travel times, and exposure error between measured and nearest standard speed.

You can find curtains travel times for most cameras in a table on a page [[Curtains Travel Times]].

> Note, Curtains travel time is presented using target distance set in settings “Frame Width” and “Frame Height”.

> The reason why it is two separate modes, is to apply correct distance ratios based on Sensor #1 geometry.

You can select between four different results representations (or modes):

![](https://github.com/srozum/film_camera_tester/blob/0dc2f6d4f6b30f7b3b05398507d5e208c369ef96/assets/screenshots/screen-6.jpg)

Measured times

- **"A"** - exposure time measured at the start of a frame. Left, Top, or Bottom depending on a type of a focal-plane shutter.
- **"B"** - exposure time measured at the center of a frame.
- **"C"** - exposure time measured at the end of a frame.
- **"S"** - measured shutter speed (exposure time at the center of a frame presented in a form "one over").
- **"To"** - travel time of an opening curtain.
- **"Tc"** - travel time of a closing curtain.

![](https://github.com/srozum/film_camera_tester/blob/0dc2f6d4f6b30f7b3b05398507d5e208c369ef96/assets/screenshots/screen-7.jpg)

Exposure errors.

Shows how much are edges of a frame over or under exposed compared to the center of a frame.

- **"A"** - calculated exposure error between start and center of a frame.
- **"B"** - exposure time measured at the center of a frame.
- **"C"** - calculated exposure error between end and center of a frame.
- **"S"** - measured shutter speed (exposure time at the center of a frame presented in a form "one over").
- **"Er"** - calculated exposure error between measured and target speed.


![](https://github.com/srozum/film_camera_tester/blob/0dc2f6d4f6b30f7b3b05398507d5e208c369ef96/assets/screenshots/screen-8.jpg)

Curtains acceleration analysis.

Helps to identify uneven travel of the curtains and issues caused by it.

- **"AB"** - curtain travel time over part of a frame from the start to the center.
- **"BC"** - curtain travel time over part of a frame from the center to the end.
- **"To"** - travel time of an opening curtain.
- **"Tc"** - travel time of a closing curtain.


![](https://github.com/srozum/film_camera_tester/blob/2ea1c309da684a7f24941bc87bdb02ca9bf8ade0/assets/screenshots/screen-21.jpg)

Curtains average travel time.

Helps to identify how consistent is curtains travel time by running series of a tests.

- **"Mn"** - fastest travel time.
- **"Av"** - average travel time.
- **"Mx"** - maximum travel time.

Left column shows results for opening curtain and right column is closing curtain.


## Average Series

This mode is very similar to “Simple Shutters” mode, except that it takes a series of measurements and presents aggregated results after last test in series. Number of tests in series is set in Setting Menu. The target speed is either detected automatically as the nearest standard speed when the selector is set to "Auto", or the selected value is used.

![](https://github.com/srozum/film_camera_tester/blob/0dc2f6d4f6b30f7b3b05398507d5e208c369ef96/assets/screenshots/screen-9.jpg)

While taking tests, the result is represented the same as in "Simple" mode, with a counter at the bottom.

![](https://github.com/srozum/film_camera_tester/blob/0dc2f6d4f6b30f7b3b05398507d5e208c369ef96/assets/screenshots/screen-10.jpg)

Summary

- **"Mn"** - minimum exposure time measured at the center of a frame.
- **"Av"** - average exposure time measured at the center of a frame.
- **"Mx"** - maximum exposure time measured at the center of a frame.
- **"S"** - average measured shutter speed (exposure time at the center of a frame presented in a form "one over").
- **"Er"** - calculated exposure error between measured and target speed.


## Flash Sync Simple

Measures Flash Sync contact Delay (X) or advance (S/M/F) of a simple shutter. The tester automatically detects X vs M delay.

The Sensor #7 (flash sync) should be connected to the Socket B.

![](https://github.com/srozum/film_camera_tester/blob/0dc2f6d4f6b30f7b3b05398507d5e208c369ef96/assets/screenshots/screen-11.jpg)

Example of measuring "M" delay of a leaf shutter camera with Copal-SV shutter.

- **X** - X-contact closes as soon as the shutter blades are close to the fully open position, usually negative number within 1-2ms.
- **M** - M-contact closes (delays shutter opening) 16-18ms before shutter blades are half-open. Values can vary for the shutters that have S/M/F modes for slow/medium/fast bulbs.


## Flash Sync Focal

Measures Flash Sync contact Delay (X) or advance (FP) of a focal-plane shutter. The tester automatically detects X vs FP delay.

The Sensor #7 (flash sync) should be connected to the Socket B.

![](https://github.com/srozum/film_camera_tester/blob/0dc2f6d4f6b30f7b3b05398507d5e208c369ef96/assets/screenshots/screen-12.jpg)

Example of measuring "X" sync (Sesnor #7 connected to the "X" terminal of a camera) of Pentax S1, which sync speed lies in between 1/30 and 1/60.

- **+X** - time between opening curtain reached end of a frame and "X" contact closed.
- **XD** - time between "X" contact closed and beginning of closing curtain travel.


![](https://github.com/srozum/film_camera_tester/blob/0dc2f6d4f6b30f7b3b05398507d5e208c369ef96/assets/screenshots/screen-13.jpg)

Example of measuring "FP" delay (Sesnor #7 connected to the "FP" terminal of a camera) of Pentax S1, which sync speed lies in between 1/30 and 1/60.

- **FP** - Time between contact closed and shutter starting to open. Values can vary for the shutters that have S/M/F modes for slow/medium/fast bulbs, for example Nikon F.


## Leaf Efficiency

This mode was developed to measure the effective speed and efficiency of leaf shutters and to collect data about the real-life efficiency of leaf shutters of various types and sizes.

> Note, that leaf shutter without a lens and with aperture fully open is implied here.

As you know, for speeds above 1/100 exposure time measured on-axis (at the center of a frame) usually differs from a nominal speed. Some technicians at the beginning of their journey (used to be me, for example) are trying to achieve an exact match between measured and specified speed by bending springs, forcing levers, etc. Don't do this. That's because the speeds scale on leaf shutters is marked in effective speeds, which were measured and set by a manufacturer using special equipment.

For example, service manual for Compur #00 shutters says that the nominal time measured on axis (at the center of a frame) for speed 1/125 should be 8.57ms instead of 10ms, or 2.7ms instead of 2ms for speed 1/500.

The diagram below illustrates the operating cycle of a leaf shutter and how effective exposure is determined. According to it, the formula of Te (effective exposure time) looks like this: Te = T2 + (T1+T3)/2.

![](https://github.com/srozum/film_camera_tester/blob/a9e86a9e29e1453685e43ca2b0b145c101124e74/assets/screenshots/screen-19.png)

Although, the operating diagram of a real shutter doesn't look like a perfect trapezoid, after many laboratories tests few assumptions were made:

- Slope of T1 and T2 could be considered linear.
- T1 and T2 could be considered equal.

Thus, Te can be calculated as an area of a trapezoid, and simple time-based measurements can be used to measure effective speed of a leaf shutter.

"Leaf Efficiency" mode utilizes this principle by taking two measurements: at the center of a shutter opening, and at the very edge of a shutter opening. Te then will be avergae of two.

Sensor #3 with a laser diode should be used in this mode.

![](https://github.com/srozum/film_camera_tester/blob/0dc2f6d4f6b30f7b3b05398507d5e208c369ef96/assets/screenshots/screen-17.jpg)

Example of measuring effective speed of a Synchro-Compur (Kodak Retina Reflex III) shutter at 1/250.

- **"Tt"** - Measurement #1: Total open time measured at the center of a shutter opening.
- **"To"** - Measurement #2: Fully open time measured at the very edge of a shutter opening, as accurate as beam of a laser diode allows.
- **"Te"** - Effective exposure time, calculated as Te = (Tt + To) / 2.
- **"Se"** - Effective shutter speed (Te presented in a form "one over").
- **"Er"** - calculated exposure error between calculated effective and target speed.
- **"Eff"** - calculated efficiency of a shutter at a target speed.

> Btw, did you know that efficiency of a focal-plane shutters is around 60% ?

## Light Source

In this mode you can test accuracy of a hand held light meters or light meters built into a cameras.

Selector sets brightness of a Light Source within 4-16EV range according to selected K value. Display prompts what meter readings or camera settings could be with set level of brightness.

![](https://github.com/srozum/film_camera_tester/blob/2ea1c309da684a7f24941bc87bdb02ca9bf8ade0/assets/screenshots/screen-20.jpg)

In this example, when ISO set to 100 and apperture to F8, camera meter should show speed 1/125.

Below is a luminance values table depending on what K Value selected in settings menu. Please note that levels are shifted by one stop. This is because older cameras with selenium or LDR photoelements read LED light source exactly one stop lower. If you are testing modern camera with a photodiode sensors, keep in mind that you have to set Light Source one step lower.

|EV   | K12.5 | K14.03 |
|---- | ----  | ----   |
|4    | 4     | 4.49   |
|5    | 8     | 8.98   |
|6    | 16    | 17.96  |
|7    | 32    | 35.92  |
|8    | 64    | 71.8   |
|9    | 128   | 143.65 |
|10   | 256   | 287.3  |
|11   | 512   | 575    |
|12   | 1024  | 1149   |
|13   | 2048  | 2299   |
|14   | 4090  | 4595   |
|15   | 8190  | 9195   |
|16   | 16390 | 18390  |

> To use this mode Light Unit #2 should be connected to the Tester.
