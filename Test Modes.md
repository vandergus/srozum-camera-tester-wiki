## Simple

This basic mode allows you to quickly test shutters of different types at various speeds. It continuously measures exposure time and calculates an exposure error between measured and target speed. The target speed is either detected automatically as the nearest standard speed when the selector is set to "Auto", or the selected value is used.

Either of the Sensors #1, #2 or #3 can be used in this mode since only the center photosensor is utilized.

![](https://github.com/srozum/film_camera_tester/blob/0dc2f6d4f6b30f7b3b05398507d5e208c369ef96/assets/screenshots/screen-4.jpg)

Results displayed ona screen:

- **"T"** - measured exposure time. Automatically formatted in s/ms/µs.
- **"S"** - measured shutter speed (time presented in a form "one over").
- **"Er"** - calculated exposure error between measured and target speed.

When testing simple or leaf shutters the measured exposure time at the center of a frame is not an actual (or effective) speed. Especially it's applies for speeds above 1/60. For example, service manual for Compur shutters says that the nominal time measured on axis (at the center of a frame) for speed 1/125 should be 8.57ms instead of 10ms, or 2.7ms instead of 2ms for speed 1/500.

## Focal Vertical / Horizizontal

In this mode, using Sensor #1, you can test cameras with focal plane shutters, and get detailed results about exposure times at three points of a frame, opening and closing curtains travel times, and exposure error between measured and nearest standard speed.

> Note, Curtains travel time is presented using target distance set in settings “Frame Width” and “Frame Height”.

> The reason why it is two separate modes, is to apply correct distance ratios based on Sensor #1 geometry.

You can select between four different results representations:

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

Curtains analysis.

Helps to identify uneven travel of the curtains and issues caused by it.

- **"AB"** - curtain travel time over part of a frame from the start to the center.
- **"BC"** - curtain travel time over part of a frame from the center to the end.
- **"To"** - travel time of an opening curtain.
- **"Tc"** - travel time of a closing curtain.


![](https://github.com/srozum/film_camera_tester/blob/2ea1c309da684a7f24941bc87bdb02ca9bf8ade0/assets/screenshots/screen-21.jpg)

Curtains average travel time.

Helps to identify how consistent is curtains travel time.

- **"Mn"** - fastest travel time.
- **"Av"** - average travel time.
- **"Mx"** - maximum travel time.

Left column shows results for opening curtain and right column is closing curtain.

## Average Series

This mode is very similar to “Simple” mode, except that it takes a series of measurements and presents aggregated results after last test in series. Number of tests in series is set in Setting Menu. The target speed is either detected automatically as the nearest standard speed when the selector is set to "Auto", or the selected value is used.

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

> To use this mode Light Unit #2 should be connected to the Tester.






