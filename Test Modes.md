## Simple

This basic mode allows you to quickly test shutters of different types at various speeds. It continuously measures exposure time and calculates an exposure error between measured and target speed. The target speed is either detected automatically as the nearest standard speed when the selector is set to "Auto", or the selected value is used.

Either of the Sensors #1, #2 or #3 can be used in this mode since only the center photosensor is utilized.

![](https://github.com/srozum/film_camera_tester/blob/0dc2f6d4f6b30f7b3b05398507d5e208c369ef96/assets/screenshots/screen-4.jpg)

Results displayed ona screen:

- **"T"** - measured exposure time. Automatically formatted in s/ms/µs.
- **"S"** - measured shutter speed (time presented in a form "one over").
- **"Er"** - calculated exposure error between measured and target speed.



## Focal Vertical / Horizizontal

In this mode, using Sensor #1, you can test cameras with focal plane shutters, and get detailed results about exposure times at three points of a frame, opening and closing curtains travel times, and exposure error between measured and nearest standard speed.

> Note, Curtains travel time is presented using target distance set in settings “Frame Width” and “Frame Height”.

> The reason why it is two separate modes, is to apply correct distance ratios

You can select between three different results representations:

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



## Flash Sync Focal

Measures Flash Sync contact Delay (X) or advance (M/F/FP)

Simple Shutter
* M
    * positive number ~16ms before shutter opening
    * values can vary be for S/M/F bulbs
* X
    * Negative number 2-4ms, happens at the time or after shutter is open

Focal Plane Shutter
* V or H can be detected and don’t matter in this test because frame width doesn’t used here
* +X / XD
* FP



## Leaf Efficiency

Compur speeds from service manual

* Takes two measurements, one at center Tt (Total open time) and one at the edge Two (wide open time
* Te (effective exposure time) = (Two + Tt)/2
* Efficiency E = (Two + Tt)/2 / Tt

## Light Source


