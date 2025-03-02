<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Eleta: A Voice-Controlled Robotic System</title>
</head>
<body>

<h1 align="center">🤖 Eleta: A Voice-Controlled Robotic System</h1>
<h2 align="center">🚀 Bringing Automation & Intelligence to Robotics</h2>

<hr>

<h2>🔍 The Problem</h2>

<p>Manually controlling robots with buttons or remotes can be inefficient and outdated. What if a robot could <b>understand voice commands</b> and respond instantly?</p>

<p>Traditional robot control methods limit accessibility, especially for those with disabilities. A voice-controlled system can revolutionize <b>personal assistance, automation, and interactive robotics</b>.</p>

<hr>

<h2>💡 The Smart Solution</h2>

<p><b>Eleta</b> is an intelligent, voice-controlled robotic system designed to <b>respond to verbal commands</b> and execute various movements like forward, backward, turning, and even performing predefined patterns.</p>

<p>Built for hobbyists, students, and tech enthusiasts, Eleta is a <b>step forward</b> in <b>automation and smart robotics</b>.</p>

<hr>

<h2>🚀 Features</h2>

<ul>
    <li>✅ <b>Voice-Controlled Movements</b> – Command Eleta to move in any direction.</li>
    <li>✅ <b>Predefined Shapes</b> – Make Eleta move in a circle, square, or hexagon.</li>
    <li>✅ <b>Bluetooth Communication</b> – Control the robot wirelessly.</li>
    <li>✅ <b>LCD Display</b> – Shows real-time commands and actions.</li>
    <li>✅ <b>Easy-to-Build</b> – Simple and effective for robotics enthusiasts.</li>
</ul>

<hr>

<h2>🛠️ How It Works</h2>

<ul>
    <li>🔹 A <b>Bluetooth module</b> receives voice commands from a paired device.</li>
    <li>🔹 An <b>Arduino</b> processes the command and executes the corresponding movement.</li>
    <li>🔹 A <b>motor driver circuit</b> controls the movement of the robot.</li>
    <li>🔹 An <b>LCD screen</b> displays the received commands.</li>
</ul>

<hr>

<h2>📜 Project Components</h2>

<ul>
    <li><b>Arduino Uno</b></li>
    <li><b>HC-05 Bluetooth Module</b></li>
    <li><b>Motor Driver (L298N)</b></li>
    <li><b>12V DC Motors</b></li>
    <li><b>16x2 LCD Display with I2C</b></li>
    <li><b>Power Supply</b></li>
</ul>

<hr>

<h2>🖥️ Arduino Code</h2>

<pre>
#include <Wire.h>
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
    case 'S': stopMotors(); lcd.print("Command: Stop"); break;
    case 'F': forward(); lcd.print("Command: Forward"); break;
    case 'B': backward(); lcd.print("Command: Backward"); break;
    case 'L': turnLeft(); lcd.print("Command: Left"); break;
    case 'R': turnRight(); lcd.print("Command: Right"); break;
    case 'C': makeCircle(); lcd.print("Command: Circle"); break;
    case 'Q': makeSquare(); lcd.print("Command: Square"); break;
    case 'H': makeHexagon(); lcd.print("Command: Hexagon"); break;
    case 'D': dance(); lcd.print("Command: Dance"); break;
    default: lcd.print("Unknown Cmd"); break;
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

void stopMotors() {
  digitalWrite(MOTOR1_PIN1, LOW);
  digitalWrite(MOTOR1_PIN2, LOW);
  digitalWrite(MOTOR2_PIN1, LOW);
  digitalWrite(MOTOR2_PIN2, LOW);
}
</pre>

<hr>

<h2>🏆 Project Outcomes</h2>

<ul>
    <li>🤖 The robot follows <b>voice commands</b> and executes movements accordingly.</li>
    <li>📡 Users can <b>remotely control</b> the robot via Bluetooth.</li>
    <li>🎯 Enables easy <b>robotic automation</b> without complex interfaces.</li>
</ul>

<hr>

<h2>📽️ Project Demos</h2>

<p>Here are some project show snapshots:</p>

<table align="center" border="0" cellpadding="10">
    <tr>
        <td align="center">
            <img src="Eleta Interacting with Human.jpg" alt="Eleta Interacting with Human" width="300">
            <p>📸 Eleta interacting with human</p>
        </td>
        <td align="center">
            <img src="eleta_voice_command.jpg" alt="Eleta Listening to Voice Commands" width="300">
            <p>📸 Eleta listening to voice commands</p>
        </td>
    </tr>
    <tr>
        <td align="center">
            <img src="eleta_showcase.jpg" alt="Eleta Showcasing at Electro Fest-04" width="300">
            <p>📸 Project showcasing at Electro Fest-04</p>
        </td>
        <td align="center">
            <img src="eleta_award.jpg" alt="Eleta Winning Award at Electro Fest-04" width="300">
            <p>🏆 Prize-giving ceremony</p>
        </td>
    </tr>
</table>

<hr>

<h2>🔗 Get Involved & Build Your Own Eleta!</h2>

<p>🚀 <b>Clone the Repository & Start Building:</b></p>

<pre>
git clone https://github.com/YourUsername/Eleta-Robot.git
</pre>

</body>
</html>
