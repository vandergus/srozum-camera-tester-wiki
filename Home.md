![](https://github.com/srozum/film_camera_tester/blob/596732486f047422b243e279404cc8ec0cb5f984/assets/images/product-small-1.jpg)

## Features and characteristics

- Measures exposure time at the center of a frame of simple (leaf) and focal plane shutters of 35mm and Medium Format (6x6 or 6x45 using adapter) cameras.
- Measures timings of focal plane shutters with cutrains traveling vertically or horizontally.
  - Results can be represented in few different ways to help you detect different flaws in a shutter operation, such as curtains capping or tapering, uneven travel speed, etc.
- Measures delays between flash contact and shutter opening.
  - Automatically identifies X, M or FP modes.
- Takes series of measurements, and calculates average stats.
  - Number of tests in series can be selected in Settings menu between 3, 5, 10 or 20.
- Automatically detects type of connected Sensors, and notifies you if wrong sensor connected for a specific Mode.
- Automatically detects target speed used to calculate the error.
  - Target speed can be set to "Auto" or pre-set from a list of standard speeds.
  - You aslo can select between two sets of standard speeds (Old style like 1/50 or New style like 1/60), depending on type of shutter you are testing.
- Automatically re-calculates curtains travel time according to selected frame width or height.
- Range of measured speeds from 1s to 1/8000
- Accuracy 10µs (measured in pre-set environment, using signal generator and specialized light source)
  - Accuracy may vary during real life measurements with different light sources and cameras.

## Main parts and components

Camera Tester uses Arduino Nano compatible board for processing. Arduino mounted on Shield PCB which connects all periferal devices to it via three sockets. Each socket has pin for automatic device identification. Device identification is based on simple resistor divider which present in each sensor or light unit. Such approach allows to make user interface much simpler.

Controls are mounted on Keypad PCB, and include Rotary Encoder, and "Mode", "Menu", "Start" and "Stop" buttons. Dedicated "Start" and "Stop" buttons are used to avoid using interrupts and increase accuracy of measurements. Thus, during the test, all other controls are disabled. Keypad itself was designed in two form factors (further named as "vertical" and "horizontal") for the convenience of mounting Tester in various enclosures.

For time based measurements you don't need a specialized light source, neither precise alighnment, etc. Best choice of light source would be a standard desk lamp with incadescent light bulb, or bright LED panel placed in front of a camera in proximity of 5-15cm. But, keep in mind, that photodiodes used for the Sensors are most sensible to red to infrared light. Thus some bright white cheap LEDs (with color temp 6500K and poor CRI) won't work, because their spectrum lies mostly in blue range.

### Sockets


**Socket A** is a main socket for connecting Sensors which are used for time based measurements. It uses 3 GPIO pins either as inputs or outputs, depending on connected Sensor. Currently, sensors #1, #2, #3 can be connected to this socket and will be recognized by a Tester.

**Socket B** is a secondary socket which has 1 GPIO pin and other two pins are I2C bus pins. Currently, only sensor #7 can be used on this socket.

> In current revision I2C pins directly connected to Socket B without a buffer. Thus, if you accidentally connect wrong Sensor to Socket B it may cause Tester to stop working.

**Light Unit Socket** is used to control Light Unit. One pin is used to turn on or off or regulate brightness of a light source with PWM signal, depending on type on connected Light Unit. Other pin is used to turn on or of the Fan of a Light Unit. And a third pin is available for any kind of feedback sense implementations.

> Unlike Socket A or B you cannot hot-swap Light Units. Light Unit must be connected before powering the Tester.

> Do not connect LED or any other load directly to Light Unit Socket pins. It's pins should be used as a control signals only.



### Sensors

**Sensor #1** - sensor with three diagonally placed photodiodes, for testing focal plane shutters. Such construction is commonly used in professional testers and allows to use it without worrying about the sensor orientation. It's frame edge designed to snuggly fit in a frame opening of most cameras without touching or damaging the curtains.

> This sensor was made in two versions: V1 with 32mmx22mm distance between furthest photodiodes, V2 with 32mmx20mm distance.

**Sensor #2** - sensor with single photodiode at the center, mainly for older cameras with simple shutters. It's frame edge is made smaller to fit older cameras, since those may have either smaller frame opening, or sprockets or some pins protruding, which will not allow you to fit bigger sensor. Also this sensor comes with an adpater for easy placement in frame opening of a medium format 6x6 or 6x45 cameras.

**Sensor #3** - sensor with single photodiode and a laser diode mounted against it, the construction you can see in other implementations of Arduino based testers. This sensor is comfortable to use when you need to test simple shutter detached from a camera. Also this sensor is required for "Leaf Efficiency" mode.

**Sensor #7** - simple sensor with standard PC connector used to test flash sync or delay timings of a cameres with simple or focal plane shutters. Instead of PC connector you may use hot shoe connector.


Schematics of each Sensor you can find on "Assembly Instructions" page.

More IDs (like #4, #5, #6, etc.) are reserved for future development. For example, sensor for medium format focal plane shutters, sensor for leica type cameras with non removable preasure plate, and others.


### Light Units

**Light Unit #1** - simple ON/OFF light unit. Added just for the convinience of use. Tester can turn on or off the light source when you press "Start" or "Stop" when running tests.

**Light Unit #2** - light unit with adjustable brightness. Controlled with PWM signal generated by a Tester. Required for "Light Source" mode. During other test modes it opreates same as unit #1.

> Schematics will be available later

### Power supply

You have few options how to power the device:
- From a 7..12V regulated or unregulated power source. Power will be regulated down to 5V by a voltage regulator of Arduino board.
- From a 5V regulated power source. Connector for a power supply wires in such case should be soldered to pins labeled as "5V"
- Via USB cable connected directly to Arduino board.
- Also, there is a reserved space and connections for small voltage regulator, in case if you chose to power device with 24V or else.

> **Allways double check the polarity of connected power source before powering the device. Device is not equiped with any protection against reversed polarity.**
