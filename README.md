# Myoelectric Circuit with EMG Sensor - Development Guide 


This circuit controls five servo motors using electromyography (EMG) signals captured by the Muscle Sensor.

The EMG envelope rectifies and amplifies the analog signals and the electrodes connected directly to (end user’s) forearm help capturing them. 

Then, each servo motor will receive an independent digital signal using the Arduino microcontroller analog-to-digital converter.

https://www.youtube.com/watch?v=NeS8_q_ePO4

# Circuit Implementation Steps 


# Muscle Sensor Power Supply Connection 

The sensor requires an external power supply maximum ±18v. 

-	Ensure to connect the positive terminal of the first 9V battery to the +Vs pin on the sensor.

-	Then, connect the negative terminal of the first 9V battery to the positive terminal of the second 9V battery and connect to the ground pin on the sensor.

-	Finally, connect the negative terminal of the second 9V battery to the –Vs pin on the sensor.


# Servo Motor Power Supply Connection 

The servo motor needs an external power supply, connect servo motor negative terminal to a ground pin on the Arduino.


# Muscle Sensor Arduino Microcontroller Connection

The sensor will provide an analog signal, connect the sensor’s signal pin into the Arduino’s analog pin and the sensor’s ground pin requires to be connected to the Arduino’s ground pin.


# Servo Motor Arduino Microcontroller Connection

The servo motor has a digital terminal that connects to the PWM pin on the Arduino.

For this project, the test was performed using five servo motors and it was declared in the Arduino code.


# Electrodes Cable’s Snap Connector Connection 

The position of the electrodes is important for the correct functionality of the myoelectric circuit

-	Place one electrode (red cable’s snap connector) in the middle of the muscle body.

-	Then, the second electrode (green cable’s snap connector) at one end of the muscle and it should line up in the direction of the muscle length.

-	Finally, connect the reference electrode (yellow cable’s snap connector) on a bony or non-adjacent muscular part. 


# Flexy-Hand Design 


The Flexy-Hand design was used as a prototype since it is from Thingiverse (https://www.thingiverse.com/thing:380665), one of the most popular open source sites, focused on CAD designs for 3D printing. 

The Flexy-Hand is completely open source, which should give a lot of designers a chance to completely customize the hand for whoever may need it.


# Myoelectric Arduino Code using EMG analog signal to control five micro-servo motors


This code uses the Arduino servo library. It was needed to define a threshold value that will move the servo motor if the EMG sensor value is above this threshold.  

The five servo motors were defined to use the PWM digital pins, and EMG signal was declared to use an analog pin. 

Additionally, int variable was declared for motion routines to provide the servo position in degrees for the hand-open and close actions. 

Finally, a loop was used to indicate when the EMG sensor value is greater than the threshold the servo motor will turn to 170 degrees, if this sensor value is less the servo motor will turn to 10 degrees. 

