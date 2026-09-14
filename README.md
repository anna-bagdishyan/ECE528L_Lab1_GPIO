# ECE 528/L - Robotics and Embedded Systems Lab
**CSU Northridge**

**Department of Electrical and Computer Engineering**

## GPIO Lab
The GPIO lab interfaces with the following:

* User buttons and LEDs of the TI MSP432 LaunchPad
* PMOD SWT (4 Slide Switches) - [Product Link](https://digilent.com/reference/pmod/pmodswt/start)
* PMOD 8LD (8 LEDs) - [Product Link](https://digilent.com/shop/pmod-8ld-eight-high-brightness-leds/)


# Known Issues or Limitations  
For Task 1, LED1 and the RGB LED were initially checked separately, which caused different starting states when pressing button two while button one was already held. The solution was to use LED1's current state to decide what both LEDs should do, which resulted in both LEDs toggling at the same time instead of relying on their previous states separately. The solution now works as intended, with all cases working correctly.  
