# Electronics Task 2
## Connect and program an electronic circuit containing 6 servo motors in a simulation program.
This project demonstrates how to control a biped robot using 6 servo motors on Tinkercad. The code moves the robot's legs to simulate walking.
### 1. Prerequisites:
* Tinkercad account
* Arduino Uno (in Tinkercad)
* Breadboard (in Tinkercad)
* 6 Servo Motors (in Tinkercad)
### 2. Circuit Diagram:
Set up the circuit in Tinkercad by following these steps:
1. Open Tinkercad and create a new circuit.
2. Drag an Arduino Uno board to the workplane.
3. Drag six servo motors to the workplane.
4. Place a breadboard on the workplane.
5. Connect the servo motors to the Arduino as follows:
* Servo 1 (Left Hip) signal wire to pin 3
* Servo 2 (Left Knee) signal wire to pin 5
* Servo 3 (Left Ankle) signal wire to pin 6
* Servo 4 (Right Hip) signal wire to pin 9
* Servo 5 (Right Knee) signal wire to pin 10
* Servo 6 (Right Ankle) signal wire to pin 11
6. Connect all servo motor power wires (red) to the positive rail of the breadboard.
7. Connect all servo motor ground wires (black) to the negative rail of the breadboard.
8. Connect the negative rail of the breadboard to a GND pin on the Arduino.
9. Add a 6V power supply to the breadboard:
* Connect the positive terminal of the power supply to the positive rail of the breadboard.
* Connect the negative terminal of the power supply to the negative rail of the breadboard.
  
![Cool Kup-Bruticus](https://github.com/Alaa3172/ElectronicsTask1/assets/173661540/35b851af-4d6a-415c-8182-f53679444256)
[Tinkercad Link](https://www.tinkercad.com/things/bKvGIck0AlD-cool-kup-bruticus/editel?sharecode=vQDAXNlZOM3ZKGdcR9xCAI1mVVrCmFDtrqCJ1-ARG0M)
### 3. Usage:
1. Open Tinkercad.
2. Copy the provided code into the code editor in Tinkercad.
3. Start the simulation.
### 4. Code Overview:
The code controls the servo motors attached to the robot's joints. Each servo represents a different part of the robot's leg (hip, knee, ankle). The main loop continuously loops through the steps to simulate walking.

#include <Servo.h>

// Define servo objects for each joint

Servo servo1;  // Left Hip

Servo servo2;  // Left Knee

Servo servo3;  // Left Ankle

Servo servo4;  // Right Hip

Servo servo5;  // Right Knee

Servo servo6;  // Right Ankle

void setup()

{
  // Attach servos to their respective pins
  
  servo1.attach(3);
  
  servo2.attach(5);
  
  servo3.attach(6);
  
  servo4.attach(9);
  
  servo5.attach(10);
  
  servo6.attach(11);
}

void loop()

{
  // Step 1: Move the right leg forward
  
  moveRightLegForward();
  
  delay(1000);  // Wait for 1 second

  // Step 2: Move the right leg back to the neutral position
  
  moveRightLegNeutral();
  
  delay(1000);  // Wait for 1 second

  // Step 3: Move the left leg forward
  
  moveLeftLegForward();
  
  delay(1000);  // Wait for 1 second

  // Step 4: Move the left leg back to the neutral position
  
  moveLeftLegNeutral();
  
  delay(1000);  // Wait for 1 second
}

void moveRightLegForward()

{
  // Position servos to move the right leg forward
  
  servo1.write(90);   // Left hip neutral
  
  servo2.write(90);   // Left knee neutral
  
  servo3.write(90);   // Left ankle neutral
  
  servo4.write(45);  // Right hip forward
  
  servo5.write(135);   // Right knee bent
  
  servo6.write(45);   // Right ankle adjusted
}

void moveRightLegNeutral()

{
  // Position servos to return the right leg to the neutral position
  
  servo1.write(90);   // Right hip neutral
  
  servo2.write(90);   // Right knee straight
  
  servo3.write(90);   // Right ankle neutral
}

void moveLeftLegForward()

{
  // Position servos to move the left leg forward
  
  servo1.write(45);   // Left hip forward
  
  servo2.write(135);   // Left knee bent
  
  servo3.write(45);  // Left ankle adjusted
  
  servo4.write(90);   // Right hip neutral
  
  servo5.write(90);   // Right knee neutral
  
  servo6.write(90);   // Right ankle neutral
}

void moveLeftLegNeutral()

{
  // Position servos to return the left leg to the neutral position
  
  servo4.write(90);   // Left hip neutral
  
  servo5.write(90);   // Left knee straight
  
  servo6.write(90);   // Left ankle neutral
}
