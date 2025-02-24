# Eleta-A-Voice-Controlled-Smart-Robot-
Welcome to the Eleta project! Eleta is an Arduino-powered robot that listens to voice commands via Bluetooth and performs tasks like moving in various directions, drawing shapes, and even dancing! This repository includes everything you need to build and customize your own Eleta robot.
![89242073_538861933431625_296384186879574016_n](https://github.com/user-attachments/assets/6a2ae08b-d48c-466f-a2dd-8dddade410cd)

Table of Contents
Project Overview
Features
Components Needed
Getting Started
Hardware Setup
Software Setup
Voice Commands
Troubleshooting
Customization Ideas
Contributing
![87181752_538860836765068_8617118758571343872_n](https://github.com/user-attachments/assets/9f1d9d7e-f044-4ab1-843c-b76e81dee3f2)

Project Overview
Eleta is an Arduino-based smart robot that can:

Execute movement commands like forward, backward, left, and right.
Draw geometric shapes such as circles and squares.
Display commands on an LCD screen.
Perform a “dance” routine when prompted.
This project is beginner-friendly and highly customizable.
![87148058_538860676765084_6000465463115513856_n](https://github.com/user-attachments/assets/c9afff4c-7ec0-4a30-868d-14129651d7f0)

Features
Voice-Controlled: Bluetooth-enabled for seamless communication.
LCD Feedback: Displays commands in real time.
Shape Drawing: Moves in pre-defined patterns like circles or squares.
Customizable: Add sensors, cameras, or new movements to enhance its capabilities.
Components Needed
Here’s the list of components you’ll need to build Eleta:

Component	Quantity	Description
Arduino (ESP32 or UNO)	1	The brain of the robot.
L298N Motor Driver	1	Controls the motors.
DC Motors	2	For movement.
Bluetooth Module (HC-05)	1	Enables voice command communication.
LCD Screen (16x2, I2C)	1	Displays the received commands.
Power Supply/Battery	1	Powers the robot.
Jumper Wires & Breadboard	As needed	For connections.
Chassis	1	Base to mount the components.
Getting Started
Hardware Setup
Follow these steps to assemble the robot:
![Eleta CKT](https://github.com/user-attachments/assets/e9c7b913-413e-412f-9209-123ab6253bf0)

Motor Connections:

Connect the DC motors to the L298N motor driver module.
Attach the motor driver module to the Arduino using the appropriate pins.
LCD Screen:

Connect the LCD to the Arduino via I2C (SDA, SCL).
Bluetooth Module:

Attach the RX and TX pins of the Bluetooth module to the Arduino.
Power Supply:

Connect the battery pack to the motor driver and Arduino.
Refer to the wiring diagram for detailed connections.

Software Setup
Install Arduino IDE:
Download and install the Arduino IDE from arduino.cc.

Add Required Libraries:

LiquidCrystal_I2C: For LCD communication.
Upload the Code:

Open Eleta.ino from this repository in Arduino IDE.
Select the correct board and port.
Upload the code to your Arduino.
Voice Commands
Eleta responds to these voice commands sent via a Bluetooth app:

Command	Action
F	Move Forward
B	Move Backward
L	Turn Left
R	Turn Right
C	Draw a Circle
Q	Draw a Square
D	Dance
S	Stop Movement
Use any Bluetooth terminal app to send these commands.

Troubleshooting
If Eleta doesn’t work as expected, try the following:

Check Connections: Ensure all components are connected securely.
Bluetooth Pairing Issues: Confirm that the Bluetooth module is paired with your smartphone.
Debugging Code: Look for error messages in the Arduino IDE and ensure all libraries are installed.
Power Issues: Verify that the battery pack provides sufficient power to the motors and Arduino.
Customization Ideas
Take Eleta to the next level with these ideas:

Add obstacle avoidance sensors for autonomous navigation.
Integrate a camera for real-time object detection.
Program advanced movement patterns like zigzag or spiral paths.
Contributing
Want to contribute to this project? 
Great! Here’s how you can help:
Driver:[LiquidCrystal_I2C-master.zip](https://github.com/user-attachments/files/18938124/LiquidCrystal_I2C-master.zip)

Code:[#include <Wire.h>
#include <LiquidCrystal_I2C.h>

// LCD Configuration
LiquidCrystal_I2C lcd(0x27, 16, 2);

// Motor Pins
#define MOTOR1_PIN1 3
#define MOTOR1_PIN2 4
#define MOTOR2_PIN1 5
#define MOTOR2_PIN2 6

// Bluetooth Input
char command = 'S'; // Default command is Stop

void setup() {
  // LCD Initialization
  lcd.init(); // Correct initialization for most LiquidCrystal_I2C libraries
  lcd.backlight();

  // Motor Pins Setup
  pinMode(MOTOR1_PIN1, OUTPUT);
  pinMode(MOTOR1_PIN2, OUTPUT);
  pinMode(MOTOR2_PIN1, OUTPUT);
  pinMode(MOTOR2_PIN2, OUTPUT);

  // Bluetooth Communication
  Serial.begin(9600);

  // Display Welcome Message
  lcd.setCursor(0, 0);
  lcd.print("Electro Fest-04");
  lcd.setCursor(0, 1);
  lcd.print("My name is Eleta");
  delay(2000);
  lcd.clear();
  lcd.setCursor(0, 0);
  lcd.print("Created by:");
  lcd.setCursor(0, 1);
  lcd.print("Rakibul & Sadi");
  delay(2000);
  lcd.clear();
}

void loop() {
  // Check if Bluetooth sends a command
  if (Serial.available()) {
    command = Serial.read();
    executeCommand(command);
  }
}

void executeCommand(char cmd) {
  lcd.clear();
  switch (cmd) {
    case 'S': // Stop
      stopMotors();
      lcd.print("Command: Stop");
      break;
    case 'F': // Forward
      forward();
      lcd.print("Command: Forward");
      break;
    case 'B': // Backward
      backward();
      lcd.print("Command: Backward");
      break;
    case 'L': // Left
      turnLeft();
      lcd.print("Command: Left");
      break;
    case 'R': // Right
      turnRight();
      lcd.print("Command: Right");
      break;
    case 'C': // Circle
      makeCircle();
      lcd.print("Command: Circle");
      break;
    case 'Q': // Square
      makeSquare();
      lcd.print("Command: Square");
      break;
    case 'H': // Hexagon
      makeHexagon();
      lcd.print("Command: Hexagon");
      break;
    case 'D': // Dance
      dance();
      lcd.print("Command: Dance");
      break;
    case 'T': // Start
      lcd.print("Command: Start");
      break;
    default:
      lcd.print("Unknown Cmd");
      break;
  }
}

void forward() {
  digitalWrite(MOTOR1_PIN1, HIGH);
  digitalWrite(MOTOR1_PIN2, LOW);
  digitalWrite(MOTOR2_PIN1, HIGH);
  digitalWrite(MOTOR2_PIN2, LOW);
}

void backward() {
  digitalWrite(MOTOR1_PIN1, LOW);
  digitalWrite(MOTOR1_PIN2, HIGH);
  digitalWrite(MOTOR2_PIN1, LOW);
  digitalWrite(MOTOR2_PIN2, HIGH);
}

void turnLeft() {
  digitalWrite(MOTOR1_PIN1, LOW);
  digitalWrite(MOTOR1_PIN2, HIGH);
  digitalWrite(MOTOR2_PIN1, HIGH);
  digitalWrite(MOTOR2_PIN2, LOW);
}

void turnRight() {
  digitalWrite(MOTOR1_PIN1, HIGH);
  digitalWrite(MOTOR1_PIN2, LOW);
  digitalWrite(MOTOR2_PIN1, LOW);
  digitalWrite(MOTOR2_PIN2, HIGH);
}

void stopMotors() {
  digitalWrite(MOTOR1_PIN1, LOW);
  digitalWrite(MOTOR1_PIN2, LOW);
  digitalWrite(MOTOR2_PIN1, LOW);
  digitalWrite(MOTOR2_PIN2, LOW);
}

void makeCircle() {
  for (int i = 0; i < 10; i++) {
    turnRight();
    delay(300);
  }
  stopMotors();
}

void makeSquare() {
  for (int i = 0; i < 4; i++) {
    forward();
    delay(1000);
    turnRight();
    delay(500);
  }
  stopMotors();
}

void makeHexagon() {
  for (int i = 0; i < 6; i++) {
    forward();
    delay(800);
    turnRight();
    delay(400);
  }
  stopMotors();
}

void dance() {
  for (int i = 0; i < 5; i++) {
    forward();
    delay(500);
    backward();
    delay(500);
    turnLeft();
    delay(500);
    turnRight();
    delay(500);
  }
  stopMotors();
}
Uploading eleta_bot.ino…]()


![89311305_538861423431676_8615333972026589184_n (1)](https://github.com/user-attachments/assets/b7b201df-3f94-41d6-a95c-de5c26b595a5)

Let’s Build Together!
If you build your own version of Eleta, feel free to share it with me! Tag me on Twitter or LinkedIn with your creations.

Happy building! 🚀
