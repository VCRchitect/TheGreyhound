This is an inexpensive, one-handed controller that uses the GP2040-CE firmware to provide as much compatibility as possible, all while staying affordable.
If you'd like to build one yourself instead of ordering one from me, here is the bill of materials:

| Device Bill of Materials         |       | 
| -------------------------------- | ----- | 
| Custom PCB (Gerbers Included)    | 1     |
| YD-2040 Microcontroller          | 1     |
| 6-Pin Analog Joystick Module     | 2     |
| Kailh Choc V1 Switches           | 17    |
| 3D Printed Low Profile Key Caps  | 17    |
| 3D Printed Shell                 | 1     |
| M2 x 8mm Screw                   | 4     |
| USB A Port                       | 1     |
| 1/4" Threaded Insert             | 1     |
| M1.7 x 6mm Screw                 | 4     |

For the microcontoller, I chose this particular variant of the RP2040 because it has USB-C and costs even less than a traditional Pi Pico. This one also has the fourth ADC broken out (GPIO29) so that you can use both sticks.

When building, make sure you solder a jumper from the VREF pinhole to the 3.3v pin on the board, otherwise you'll get some bizarre behaviors with the analog sticks. Usually those YD-2040s will come with a four-pin right-angle header, and I just use it to bridge between.

For the joysticks, order the CABE-3D Analog Joystick from Aliexpress as they're the only ones I've found that don't require one of the thin ribbon-wire connectors. They work pretty well.

The 1/4" insert is designed to attach to a tripod or some similar armature for those that have difficulty holding things or don't have a table/chair arm they can put the controller on.

If you'd like to see some demos or need a video manual for using the device, visit this YouTube video:
https://youtu.be/GY2SG22l3gY

Once you've entered the web configurator, go to Settings, then Data Backup and Restoration. Load in the gp2040 configuration file that it's in this repository. Once you've done that, go to Periperal Mapping under Settings. Toggle off the i2c setting, then toggle on the USB Host setting. Pick GPIO0 for the D+ line. Choose D+/D- under Pin Order. This will enable the use of USB passthrough for the PS4 and such.
