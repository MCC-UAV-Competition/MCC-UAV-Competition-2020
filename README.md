# MCC-UAV-Competition-2020
TYESA UGV Sample Code
Description
This code is designed for the TYESA 2020 UAV Competition. This code is capable of controlling a ground vehicle that detaches from a UAV and follows a black line on a white background.

The settings below can be altered to change the configuration of the code.

The RED_THRESHOLD determines how sensitive the color sensor will be when detecting red, the lower the value, the more sensitive the sensor will be.
The RED_COUNT_TRIGGER determines how many red detection readings need to be seen in a row before dropping the UGV from the UAV. If you have trouble detecting 20 readings in a row before the count resets, try lowering the RED_THRESHOLD value so red is detected more easily.
The MS_DELAY_BETWEEN_SENSOR_READINGS determines how long to pause between color sensor readings. Effectively, the time from the first red detection to the release of the robot is going to be (RED_COUNT_TRIGGER * MS_DELAY_BETWEEN_SENSOR_READINGS). As an example, the default values are 20 and 200 so it would be 20 * 200 = 4000ms or four seconds. Adjust either value as necessary to increase or decrease this duration.
The SERVO_ENGAGE_POSITION defines the angle required for the servo to mount the UGV to the UAV
The SERVO_DISENGAGE_POSITION defines the angle required to disengage (detach) the UGV from the UAV
Regarding Menu Options, Calibration will always commence once upon startup, however, afterward the menu options control what the code will do.

Runs the line sensor calibration (though this doesn't clear any existing calibration)
Engages the servo, this is intended to be used to attach the UGV to the UAV
Disengages the servo, this is intended to be used to remove the UGV from the UAV
Starts the Detect sequence to look for red and once the variables are met, detach the robot and line follow
Displays QTR sensor readings using calibrated values (good for testing your hookup and calibration)
Stops the current action, intended for stopping the Detect sequence which also resets the red count
Note: Inputs that are not recognized will also call option 4, the stop command

Setup
Download Source
Because this is written in a different IDE than the Arduino IDE it's not a .ino file so it cannot be directly downloaded and opened in the Arduino IDE. The simplest way to use this code is to:

Open the src folder (above)
Click the main.cpp file
Select the "Raw" button in the upper right of the code window
Copy the code from the browser
Paste the code in a new Arduino sketch
Setup Libraries
The included libraries will need to be installed through the library manager, a guide is provided here https://www.digikey.com/en/maker/blogs/2018/how-to-install-arduino-libraries.

The libraries can be found here:

QTR Sensor Array - https://github.com/gberl001/qtr-sensors-arduino.git
Motor Driver - https://github.com/mcc-robotics/Dynamic_Motor_Driver
Additional Notes
If using a Teensy, the Teensyduino program will have to be installed on your computer to allow the Teensy to work with the Arduino IDE. Download from the included link https://www.pjrc.com/teensy/td_download.html

It is helpful to view the instructional videos at: http://robotresearchlab.com/2019/03/13/build-a-custom-pid-line-following-robot-from-scratch

Credit to Professor Berl for creating these videos, they are extremely helpful and detailed about how to build and program a line follow robot.

Note: Students are encouraged to build off this code, or change it if they have any ideas to make it better. This code is also specifically written to work with the Teensy and other UGV equipment outlined in the rules. Other microcontrollers and equipment can be used, but the code may need to be modified to work with your specific equipment.

A laptop is also highly recommended for the competition to attach the UGV to the UAV before flight.
