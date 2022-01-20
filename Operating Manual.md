The current version of firmware is 2.3 and it has following test modes implemented.

- Simple
- Focal Vertical
- Focal Horizizontal
- Average Series
- Flash Sync Simple
- Flash Sync Focal
- Leaf Efficiency
- Light Source

## Selecting a Mode

To select the Test Mode press the "Mode" button. Using a rotary encoder knob select which mode you want to run, and confirm your selection by pressing the knob.

Then, depending on the selected Mode and type of camera you are testing, connect a required sensor. Most of the time you'll use Sensor #1.

> **Although Tester supports sensors hot-swap, it is recommended to power off the Tester when connecting or disconnecting sensors**

When the correct sensor is connected,  and the Tester is ready to take measurements, you'll see "Press Start" on the screen. Otherwise, it will tell "Not Ready".
Similar projects that helped me to start my own

![](https://github.com/srozum/film_camera_tester/blob/0dc2f6d4f6b30f7b3b05398507d5e208c369ef96/assets/screenshots/screen-1.jpg)

The first row of the screen is a Status Bar. It tells you what sensors are connected to the Sockets A and B, the short name of selected Test Mode, and on a righthand of a line, there is an indicator of a selector for a primary setting of the Mode.

## Settings Menu

The Camera Tester has a Settings Menu for the items,  which are stored in EEPROM memory.

**Speeds Range** lets you select between two sets of standard shutter speeds, depending on what camera you are testing - "New" (with speeds marked as 1/60, 1/125, etc.) or "Old" (with speeds like 1/50, 1/100).

- "New" range goes from 8s speed to 1/8000.
- "Old" range goes from 1s to 1/1000.

**Test Series** sets the number of how many tests should be taken in average measuring modes before calculating and displaying the summary results.

- Choises are 3, 5, 10, or 20 tests in a series.

**Frame Width** sets the target distance used to present curtains travel times. Curtains travel time can be presented as it was measured at a distance between far-most openings of a Sensor, or re-calculated over distance whichever is specified in service manual for a tested camera.

For example, the service manual for a Pentax K1000 says that the edge-to-edge travel time should be 14ms, or 13.3ms over the distance of 34mm, or 12.5ms over the distance of 32mm. But more common to see travel times specified as edge-to-edge. Since the horizontal distance between the far most photodiodes of a Sensor #1 is 32mm,  it is required to do some simple math to find out the travel time over the target distance vs the sensor's space. By setting the "Frame Width", results of focal plane shutter Test Modes will be automatically re-calculated for a set distance.

> The Tester automatically detects connected Sensor and thus knows what is a distance between photosensors.

**Frame Height** similar to "Frame Width" but applying to focal plane shutters with vertical curtains travel direction.

**Sound On/Off** enables or disables buzzer sounds.

To change settings in Settings Menu press the "Menu" button. Using a rotary encoder knob select which setting you want to edit and push the knob. Blinking symbol will appear next to the value, and you can change it by rotating a retary encoder knob. Pressing it again will store the selected value in a memory. To exit the Settings Menu, scroll down to the end of a list and select "Exit menu" item.

## Taking Measurements

Open the camera back and place the Sensor into a frame opening. For the cameras with focal-plane shutters, the orientation of a Sensor doesn't matter since the Tester automatically detects the direction of the curtains. When testing cameras with a detachable lens it is recommended to remove the lens, otherwise set the aperture wide open.

> Sensor #1 has a thread mount on its back in case you want to build a rig for holding it in an upright position.

> Sensor #2 has a "+" symbol on its back to help position it in a center of a frame in case of testing half-frame cameras.

Turn on the Light Source, unless it is a Light Unit controlled by the Tester, and place it in front of a camera approximately 5-10cm away.

When ready, press the "Start" button. At this moment the Tester should say "Running..." which means it is waiting for a shutter to be fired. Fire the shutter and if the test was successful you'll hear the "beep" and results will be printed on a screen immediately.

In all modes, except "Average Series", once the first test was taken and results were printed, you will no see "Running...", instead continue taking tests and fresh results will be displayed on a screen.

To change the Test Mode or Settings, press "Stop". Because during the Test all other controls are disabled.



