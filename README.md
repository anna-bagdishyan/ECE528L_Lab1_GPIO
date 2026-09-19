# ECE 528/L - Robotics and Embedded Systems Lab
**CSU Northridge**

**Department of Electrical and Computer Engineering**

## GPIO Lab
The GPIO lab interfaces with the following:

* User buttons and LEDs of the TI MSP432 LaunchPad
* PMOD SWT (4 Slide Switches) - [Product Link](https://digilent.com/reference/pmod/pmodswt/start)
* PMOD 8LD (8 LEDs) - [Product Link](https://digilent.com/shop/pmod-8ld-eight-high-brightness-leds/)

## Overview
Brief description of the lab

## Components Used
| Components Used | Quantity    | Manufacturer 
| -------------   | ----------- | -----------
| MSP432 Launchpad  | 1 | Texas Instruments
| USB-A to Micro-USB Cable  | 1 | N/A
| PMOD 8LD   | 1 | Digilent
| PMOD SWT  | 1 | Digilent

## Analysis and Results
### Task 1
![c1_button1](https://github.com/anna-bagdishyan/ECE528L_Lab1_GPIO/blob/main/Screenshots/BTN1.jpeg)
Figure 1 - Output when pressing button 1
![c2_button2](https://github.com/anna-bagdishyan/ECE528L_Lab1_GPIO/blob/main/Screenshots/BTN2.jpeg)
Figure 2 - Output when pressing button 2  

[Video Demonstration for Pressing Buttons 1 and 2](https://drive.google.com/file/d/1JRtJ3LKuMM4ayPIyrd5ffgvNEReiE5cq/view)
### Task 2
[Video Demonstration for the Binary Down Counter](https://drive.google.com/file/d/1CkEUqCtcdnmVcqPl6F0NkIXCTbB5D32w/view?usp=sharing)
### Task 3
[Video Demonstration for the Ring Counter](https://drive.google.com/file/d/1caqgdpvGL_xEXrpimUR5ggYx_9dB8d1F/view?usp=sharing)
### Task 4
[Video Demonstration for the Reverse Ring Counter](https://drive.google.com/file/d/1QtAzT2lojmVvRV9_Qudliniqvj-1X7c_/view?usp=sharing)
### Task 5
[Video Demonstration for the Johnson Counter](https://drive.google.com/file/d/1jDJZvJWaLhZxqLTP-LBvwgomzrn5TJaC/view?usp=sharing)


## Known Issues or Limitations  
For Task 1, LED1 and the RGB LED were initially checked separately, which caused different starting states when pressing button two while button one was already held. The solution was to use LED1's current state to decide what both LEDs should do, which resulted in both LEDs toggling at the same time instead of relying on their previous states separately. The solution now works as intended, with all cases working correctly.  

For Task 3, initially the ring counter would only reach the second-to-last LED before restarting. This happened because led_count was shifted using `led_count >>= 1` before the if statement checked whether led_count was 0x01. Because of this, when led_count reached 0x01, it was shifted to 0x00 before the condition could detect it, so the counter restarted before displaying the final LED. To fix this, the shift operation was placed inside the else statement. This allows the program to check if led_count is 0x01 and reset it to 0x80. If it has not, the value is shifted to continue the sequence. The ring counter now displays the correct LED pattern.

## Author Contribution
Specify individual contributions to the lab. Optional if you’re working on your own. Bullet list is fine

## References
ECE 528/L Lab 0 - General Purpose Input Output (GPIO).
