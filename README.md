<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Eleta – A Voice-Controlled Smart Robot</title>
</head>
<body>

<h1>🤖 Eleta – A Voice-Controlled Smart Robot</h1>

<h2>🔊 Bringing Automation to Life with Simple Voice Commands</h2>

<h3>🚨 The Problem: A Need for Smarter, Hands-Free Control</h3>
<p>We live in an era where automation is revolutionizing industries, but why is controlling robots still complicated? Many robotics systems rely on physical buttons or complex programming, making them less accessible to everyone.</p>
<p>What if you could simply <b>command a robot with your voice</b> and make it move, turn, or even perform pre-programmed tasks effortlessly? That’s where <b>Eleta</b> comes in!</p>

<h3>💡 The Smart Solution: Meet Eleta, Your Voice-Controlled Assistant</h3>
<p><b>Eleta</b> is an <b>interactive voice-controlled robot</b> that responds to commands via Bluetooth, allowing users to control its movement and predefined actions with ease. Whether for educational, industrial, or entertainment purposes, Eleta showcases the power of automation and intelligent control.</p>

<hr>

<h2>🛠️ Features</h2>
<ul>
    <li>🎙️ <b>Voice-Controlled Navigation</b> – Move Forward, Backward, Left, Right, or Stop with simple commands.</li>
    <li>🔄 <b>Pre-Programmed Movements</b> – Perform Circles, Squares, Hexagons, and even Dance routines.</li>
    <li>📡 <b>Wireless Bluetooth Connectivity</b> – Control the robot using a smartphone or external device.</li>
    <li>📟 <b>LCD Display</b> – Shows current command and status updates in real time.</li>
    <li>🔋 <b>Energy Efficient</b> – Runs on a lightweight battery for extended performance.</li>
</ul>

<hr>

<h2>⚙️ How It Works</h2>
<p>Eleta listens to your voice commands sent via a Bluetooth module, processes them using an <b>Arduino microcontroller</b>, and controls the motors accordingly. It’s designed to be interactive and simple to use!</p>

<p><b>✨ Key Process Flow:</b></p>
<ol>
    <li>🔹 The user speaks a command, which is transmitted via Bluetooth.</li>
    <li>🔹 The Arduino reads the command and determines the required action.</li>
    <li>🔹 Motor drivers activate the robot’s movement accordingly.</li>
    <li>🔹 The LCD screen displays the current action.</li>
</ol>

<hr>

<h2>🌍 Why This Project Matters for the Future?</h2>
<ul>
    <li>✅ <b>Hands-Free Accessibility</b> – Ideal for users with mobility challenges.</li>
    <li>✅ <b>Educational Value</b> – A great tool for learning about robotics and automation.</li>
    <li>✅ <b>Innovation in Automation</b> – Shows the potential of integrating AI with robotics.</li>
    <li>✅ <b>Customizable & Scalable</b> – Can be enhanced with AI, IoT, or home automation features.</li>
</ul>

<hr>

<h2>🔮 Future Enhancements</h2>
<ul>
    <li>🚀 <b>AI Integration</b> – Implementing machine learning for intelligent decision-making.</li>
    <li>🎮 <b>App Control</b> – Developing a smartphone app for easier manual control.</li>
    <li>🗣️ <b>Multilingual Support</b> – Expanding voice command recognition to different languages.</li>
    <li>🤖 <b>Autonomous Navigation</b> – Using sensors for obstacle avoidance and smart path planning.</li>
</ul>

<hr>

<h2>🖥️ Project Components</h2>
<ul>
    <li><b>Arduino Uno</b></li>
    <li><b>HC-05 Bluetooth Module</b></li>
    <li><b>Motor Driver (L298N)</b></li>
    <li><b>12V DC Motors</b></li>
    <li><b>16x2 I2C LCD Display</b></li>
    <li><b>Battery Pack</b></li>
    <li><b>Wheels & Chassis</b></li>
</ul>

<hr>

<h2>💻 Arduino Code</h2>
<pre>
#include &lt;Wire.h&gt;
#include &lt;LiquidCrystal_I2C.h&gt;

LiquidCrystal_I2C lcd(0x27, 16, 2);
#define MOTOR1_PIN1 3
#define MOTOR1_PIN2 4
#define MOTOR2_PIN1 5
#define MOTOR2_PIN2 6
char command = 'S';

void setup() {
    lcd.begin();
    lcd.backlight();
    pinMode(MOTOR1_PIN1, OUTPUT);
    pinMode(MOTOR1_PIN2, OUTPUT);
    pinMode(MOTOR2_PIN1, OUTPUT);
    pinMode(MOTOR2_PIN2, OUTPUT);
    Serial.begin(9600);
}

void loop() {
    if (Serial.available()) {
        command = Serial.read();
        executeCommand(command);
    }
}

void executeCommand(char cmd) {
    lcd.clear();
    switch (cmd) {
        case 'S': stopMotors(); lcd.print("Stop"); break;
        case 'F': forward(); lcd.print("Forward"); break;
        case 'B': backward(); lcd.print("Backward"); break;
        case 'L': turnLeft(); lcd.print("Left"); break;
        case 'R': turnRight(); lcd.print("Right"); break;
        default: lcd.print("Unknown Cmd"); break;
    }
}
</pre>

<hr>

<h2>🏆 Project Outcomes</h2>
<ul>
    <li>🤖 Eleta successfully responds to voice commands, providing a seamless user experience.</li>
    <li>🎓 The project serves as an educational tool for robotics enthusiasts and students.</li>
    <li>🌍 Potential applications in smart home automation and assistive technology.</li>
</ul>

<hr>

<h2>📌 Contribution & Support</h2>
<p>Love this project? Give it a ⭐ and contribute to making Eleta even smarter!</p>
<p>Fork the repo, improve the code, and submit a pull request to add new features.</p>
<p>📩 For suggestions or collaborations, contact <b><a href="mailto:rakibul10x@gmail.com">rakibul10x@gmail.com</a></b>.</p>

<hr>

<h2>🔗 Clone the Repository & Build Your Own Eleta</h2>
<pre>
git clone https://github.com/YourUsername/Eleta-Voice-Robot.git
</pre>

</body>
</html>
