# MephistoExclusiveInterface

The two mephisto.* files are needed to read out the reed switches and control the LEDs of a Mephisto Modular/Exclusive/München chessboard.

# Following hardware components are required:
40-pin edge card connector

I am using a connector with a ribbon cable, see image.

# How to connect the 40-pin plug to the Mephisto board?

If you look at the chessboard or module from the front, the upper row of contacts is numbered from left to right from 1 to 39, the lower row from 2 to 40.
However, using different ribbon cable connectors, I experienced that the odd (top) and even (bottom) contacts are swapped (see my image)!

Only 14 pins are required to be able to light the LEDs and read out the reed switches from the chessboard:
* D0-D7 are pins 15 to 22
* LDC_EN is pin 29
* CB_EN  is pin 30
* ROW_LE is pin 31
* LDC_LE is pin 32

* VCC is pin 1 and pin 2 (both 5V and 3.3V are working for me, ESP32 CANNOT BE DRIVEN WITH 5V!)
* GND is pin 39 and pin 40

See mephisto.h file to see which cable is connected to which GPIO pin of your microcontroller.
