# Servo Motor Actuation for Robot Walking
## Introduction 
n this report, we will discuss a simple algorithm to control servo motors to simulate walking motion for a robot. The algorithm is designed for a quadruped robot (four-legged robot) and uses six servo motors to achieve the walking motion. The goal is to create a coordinated sequence of movements that allows the robot to walk forward.

## Components 
* Arduino Uno
* 6 Servo Motors
* Breadboard
* Connecting Wires

### Initial Setup
1. Define Serovo Motors:
   * Assign each servo motor to a specific pin on the Arduino.
2. Initialize Angles:
   * Define the initial and final angles for each servo motor to simulate the leg movements.
### The Steps
1. Initialization
   * Set up the servo motors and move them to their starting positions
2. Front Legs Movement:
   * Lift the front legs.
   * Move the front legs forward.
   * Lower the front legs to the ground.
3. Back Legs Movement:
   * Lift the back legs.
   * Move the back legs forward.
   * Lower the back legs to the ground.
4. Repear:
   * Repeat the steps to create a continuous walking motion.
## Implementation
Now for the code we are using C++ to implement the walking algorithm.
'''
#include <Servo.h>

// Define the servo motors
Servo servoFrontLeft;
Servo servoFrontRight;
Servo servoBackLeft;
Servo servoBackRight;

// Define initial and final angles for the servo motors
int frontLeftUp = 45;
int frontLeftDown = 90;
int frontRightUp = 45;
int frontRightDown = 90;
int backLeftUp = 45;
int backLeftDown = 90;
int backRightUp = 45;
int backRightDown = 90;

void setup() {
  // Attach the servo motors to the respective pins
  servoFrontLeft.attach(3);
  servoFrontRight.attach(5);
  servoBackLeft.attach(6);
  servoBackRight.attach(9);

  // Move the servos to the initial position
  servoFrontLeft.write(frontLeftDown);
  servoFrontRight.write(frontRightDown);
  servoBackLeft.write(backLeftDown);
  servoBackRight.write(backRightDown);
}

void loop() {
  // Lift the front legs
  servoFrontLeft.write(frontLeftUp);
  servoFrontRight.write(frontRightUp);
  delay(500); // Wait for the movement to complete

  // Move the front legs forward
  servoFrontLeft.write(frontLeftDown);
  servoFrontRight.write(frontRightDown);
  delay(500); // Wait for the movement to complete

  // Lift the back legs
  servoBackLeft.write(backLeftUp);
  servoBackRight.write(backRightUp);
  delay(500); // Wait for the movement to complete

  // Move the back legs forward
  servoBackLeft.write(backLeftDown);
  servoBackRight.write(backRightDown);
  delay(500); // Wait for the movement to complete
}
'''

