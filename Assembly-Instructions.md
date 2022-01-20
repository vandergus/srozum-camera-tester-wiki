## Shield Board

First, choose how you going to power the device:

 - From a 5V regulated power source.
   - 2 pin connector for a power supply in such case should be soldered to pins labeled on Shield PCB as "5V". Make sure to rotate the connector correctly, so that the red wire goes to "+" and the black wire goes to "-" labels above the "5V" label.
 - From a 7..12V regulated or unregulated power source.
   - Power will be regulated down to 5V by a voltage regulator of Arduino board. 2 pin connector for a power supply in such case should be soldered to pins labeled on Shield PCB as "7-12V". Make sure to rotate the connector correctly, so that the red wire goes to "+" and the black wire goes to "-" labels above the "7-12V" label.
 - Also, there is space and connections for a small voltage regulator and a screw terminal block, in case you chose to power the device from a 24V rail. This option exists because one of the prototypes is using a 24V power supply to power the Light Unit.

Second, choose how you want to connect Shield PCB to an LCD Module. You have a few options here:

 - You can sandwich Shield PCB and LCD Module together using provided standoffs. As you can see, the dimensions of a Shield PCB are the same as of LCD Module with matching holes for a 4 pin connector and brightness adjustment potentiometer. In that case, straighten 4 pins of the LCD module and make sure they fit into corresponding holes in Shield PCB. Note, you may need to adjust the distance between the LCD module and Shield PCB by either re-soldering the I2C module or by adjusting the height of standoffs.
 - If you plan to mount Shield PCB separately from LCD Module then solder provided 4 pin JST socket onto Shield PCB and replace LCD 4 pin headers with provided 4 pin JST connector with attached wires.

Then, simply solder all components and connectors following the labels on Shield PCB.


![Shield Schematics](https://github.com/srozum/film_camera_tester/blob/596732486f047422b243e279404cc8ec0cb5f984/assets/schematics/shield-v2-rev-2.png)



## Keypad

- Solder components in place: a rotary encoder and four buttons
- Solder wires from a 9 pin JST connector starting with Black to "Gnd", Red to "Vcc", and so on.

![Shield Schematics](https://github.com/srozum/film_camera_tester/blob/596732486f047422b243e279404cc8ec0cb5f984/assets/schematics/keypad.png)



## Sockets

You have two identical Socket Connectors used for connecting Sensors. Simply follow the schematics on how to solder wires between 6 pin JST connector and 6 pin GX-16 Socket.


![Socket Schematics](https://github.com/srozum/film_camera_tester/blob/596732486f047422b243e279404cc8ec0cb5f984/assets/schematics/sockets.png)




## Sensor #1

 1. Sand down the ledge of the photodiodes next to the photodiode's lens. Be careful, not to damage the lens.
 2. Using PCB as a stencil, drill three 0.8mm holes in the sensor faceplate and countersink them with a 1.8-2mm drill so the photodiode's lens fits flat in it.
   - ![Face Plate](https://github.com/srozum/film_camera_tester/blob/596732486f047422b243e279404cc8ec0cb5f984/assets/schematics/sensor-face-plate.png)
   - Note that 0.8mm is a recommended size for a sensor opening. You may use 1mm drill bit, but larger than 1mm opening will affect accuracy of a measurements.
 3. Using PCB as a stencil, bend the photodiode's legs at a proper distance, so the lens is aligned with faceplate openings.
 4. Solder photodiodes onto PCB so that distance between PCB and photodiode's back surface is approximately 4mm
   - insert foam pads between each photodiode and PCB.
 5. Make sure that all three photodiodes fit into faceplate drilled openings and sit flat against the faceplate. Bend them as needed.
 6. Enclosure assembly
  - slightly sand faceplate and body edges for better adhesion, glue face to the body
  - heat and melt in the threaded insert into the lid
  - check how every part fits, clean and sand if needed
 7. Solder cable wires according to the schematics
 8. Install PCB, make sure that sensors are aligned with openings, and fix it with 2 screws
  - make sure that drilled openings are clean
 9. Solder socket connector according to the schematics
 10. Put a zip tie on a cable to prevent it from sliding out of the enclosure
 11. Close the lid, or glue it if you want.

![Sensor #1 Schematics](https://github.com/srozum/film_camera_tester/blob/596732486f047422b243e279404cc8ec0cb5f984/assets/schematics/sensor1-v1.png)



## Sensor #2

 1. Sand down the ledge of the photodiode next to the photodiode's lens. Be careful, not to damage the lens.
 2. Using PCB as a stencil, drill a 0.8mm hole in the sensor faceplate and countersink it with a 1.8-2mm drill so the photodiode's lens fits flat in it.
   - Note that 0.8mm is a recommended size for a sensor opening. You may use a 1mm drill bit, but larger than a 1mm opening will affect the accuracy of measurements.
 3. Using PCB as a stencil, bend the photodiode's legs at a proper distance, so the lens is aligned with the faceplate opening.
 4. Solder photodiode onto PCB
 6. Enclosure assembly
  - check how every part fits, clean and sand if needed
 7. Solder cable wires according to the schematics
 8. Install PCB, make sure that sensor is aligned with the opening, and fix it with 2 screws
  - make sure that drilled opening is clean
 9. Solder socket connector according to the schematics
 10. Fix cable with a zip tie to prevent it from sliding out of the enclosure, close the lid

![Sensor #1 Schematics](https://github.com/srozum/film_camera_tester/blob/596732486f047422b243e279404cc8ec0cb5f984/assets/schematics/sensor2-v1.png)



## Sensor #7

Sensor #7 is a simple sensor used to test Flash Sync contacts of a camera. You can use some old extension cable from a flash unit. ID and pull-up resistors can fit inside of a GX-16 Socket.

![Sensor #1 Schematics](https://github.com/srozum/film_camera_tester/blob/596732486f047422b243e279404cc8ec0cb5f984/assets/schematics/sensor7.png)




