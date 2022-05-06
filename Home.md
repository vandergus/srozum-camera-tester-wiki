![](https://github.com/srozum/film_camera_tester/blob/596732486f047422b243e279404cc8ec0cb5f984/assets/images/product-small-1.jpg)

## Features and characteristics (Firmware 2.5)

- Measures exposure time at the center of a frame of simple (leaf) and focal plane shutters of 35mm and Medium Format (6x6 or 6x45 using adapter) cameras.
- Measures timings of focal plane shutters with curtains traveling vertically or horizontally.
  - Results can be represented in a few different ways to help you detect different flaws in a shutter operation, such as curtains capping or tapering, uneven travel speed, etc.
- Measures delays between flash contact and shutter opening.
  - Automatically identifies X, M, or FP modes.
- Takes a series of measurements, and calculates average stats.
  - Number of tests in series can be selected in the Settings menu between 3, 5, 10, or 20.
- Automatically detects the type of connected Sensors, and notifies you if wrong sensor is connected for a specific Mode.
- Automatically detects target speed used to calculate the error.
  - Target speed can be set to "Auto" or pre-set from a list of standard speeds.
  - You also can select between two sets of standard speeds (Old style like 1/50 or New style like 1/60), depending on the type of shutter you are testing.
- Automatically re-calculates curtains travel time according to selected frame width or height.
- Range of measured speeds from 1s to 1/8000
- Accuracy 10µs (measured in the pre-set environment, using a signal generator and specialized light source)
  - Accuracy may vary during real-life measurements with different light sources and cameras.
- Allows to check accuracy and calibrate light meters and light meters built into a cameras.
  - Light Source brightness is adjustable within 4-16EV range
  - Light Source can be switched between K12.5 and K14.03

## Main parts and components

Camera Tester uses Arduino Nano compatible board for processing. Arduino mounted on Shield PCB which connects all peripheral devices to it via three sockets. Each socket has a pin for automatic device identification. Device identification is based on a simple resistor divider,  which is present in each sensor or light unit. Such approach allows to make the user interface much simpler.

Controls are mounted on Keypad PCB, and include Rotary Encoder, and "Mode", "Menu", "Start" and "Stop" buttons. Dedicated "Start" and "Stop" buttons are used to avoid using interrupts and increase the accuracy of measurements. Thus, during the test, all other controls are disabled. Keypad itself was designed in two form factors (further named as "vertical" and "horizontal") for the convenience of mounting Tester in various enclosures.

For time-based measurements, you don't need a specialized light source, either a precise alignment, etc. The best choice of light source would be a standard desk lamp with an incandescent light bulb or bright LED panel placed in front of a camera in the proximity of 5-15cm. Recommended brightness is about 15EV, however, the Tester will work within a range of 13-16EV and readings may vary slightly. But, keep in mind, that photodiodes used for the Sensors are most sensitive to red to infrared light. Thus some bright white cheap LEDs (with color temp 6500K and poor CRI) won't work, because their spectrum lies mostly in the blue range.

### Sockets


**Socket A** is the main socket for connecting Sensors which are used for time-based measurements. It uses 3 GPIO pins either as inputs or outputs, depending on the connected Sensor. Currently, sensors #1, #2, #3 can be connected to this socket and will be recognized by a Tester.

**Socket B** is a secondary socket that has 1 GPIO pin and the other two pins are I2C bus pins. Currently, only sensor #7 can be used on this socket.

> In the current revision I2C pins are directly connected to Socket B without a buffer. Thus, if you accidentally connect the wrong Sensor to Socket B it may cause the Tester to stop working.

**Light Unit Socket** is used to control the Light Unit. One pin is used to turn on or off or regulate the brightness of a light source with a PWM signal, depending on the type of connected Light Unit. Another pin is used to turn on or off the Fan of a Light Unit. And a third pin is available for any kind of feedback sense implementations.

> Unlike Socket A or B you cannot hot-swap Light Units. The light Unit must be connected before powering the Tester.

> Do not connect LED or any other load directly to Light Unit Socket pins. Its pins should be used as control signals only.



### Sensors

**Sensor #1** - sensor with three diagonally placed photodiodes, for testing focal plane shutters. Such construction is commonly used in professional testers, also allows to use it without worrying about the sensor orientation. Its frame edge is designed to snuggly fit in a frame opening of most cameras without touching or damaging the curtains.

> This sensor was made in two versions: V1 with 32mmx22mm distance between furthest photodiodes, V2 with 32mmx20mm distance.

**Sensor #2** - sensor with single photodiode at the center, mainly for older cameras with simple shutters. Its frame edge is made smaller to fit older cameras, since those may have either smaller frame openings, sprockets, or some pins protruding, which will not allow you to fit a bigger sensor. Also, this sensor comes with an adapter for easy placement in the frame opening of a medium format 6x6 or 6x45 cameras.

**Sensor #3** - sensor with a single photodiode and a laser diode mounted against it, the construction you can see in other implementations of Arduino-based testers. This sensor is comfortable to use when you need to test a simple shutter detached from a camera. Also, this sensor is required for the "Leaf Efficiency" mode.

**Sensor #7** - simple sensor with standard PC connector used to test flash sync or delay timings of a camera with simple or focal plane shutters. Instead of a PC connector, you may use a hot shoe connector.


Schematics of each Sensor you can find on the "Assembly Instructions" page.

More IDs (like #4, #5, #6, etc.) are reserved for future development. For example, a sensor for medium format focal plane shutters, a sensor for Leica-type cameras with non-removable pressure plate, and others.


### Light Units

**Light Unit #1** - simple ON/OFF the light unit. Added just for the convenience of use. The tester can turn on or off the light source when you press "Start" or "Stop" when running tests.

**Light Unit #2** - light unit with adjustable brightness. Controlled with PWM signal generated by a Tester. Required for "Light Source" mode. During other test modes, it operates the same as unit #1.


### Power supply

You have a few options how to power the device:


- From a 7..12V regulated or unregulated power source. Power will be regulated down to 5V by a voltage regulator of the Arduino board.
- From a 5V regulated power source. Connector for a power supply wires in such case should be soldered to pins labeled as "5V"
- Via USB cable connected directly to Arduino board.
- Also, there is a reserved space and connections for a small voltage regulator, in case you chose to power the device with 24V or else.

> **Always double-check the polarity of the connected power source before powering the device. The device is not equipped with any protection against reversed polarity.**
