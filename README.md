<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Eleta – A Voice-Controlled Smart Robot 🤖</title>
</head>
<body>
    <h1>Eleta – A Voice-Controlled Smart Robot 🤖</h1>
    
    <h2>Subtitle</h2>
    <p>An innovative voice-controlled robot designed to execute commands seamlessly through Bluetooth communication.</p>
    
    <h2>The Problem</h2>
    <p>In an era of automation and AI, human-machine interaction remains limited. Many robots require manual control, making them less intuitive for users.</p>
    
    <h2>The Smart Solution</h2>
    <p>Eleta bridges this gap by enabling voice-controlled movement. With a simple voice command, users can direct the robot to move, dance, or follow predefined patterns.</p>
    
    <h2>Features</h2>
    <ul>
        <li>Voice Command Execution</li>
        <li>Bluetooth Connectivity with Android Devices</li>
        <li>Multiple Motion Patterns (Circle, Square, Hexagon, Dance)</li>
        <li>LCD Display for Real-Time Feedback</li>
        <li>Efficient Motor Control for Smooth Navigation</li>
    </ul>
    
    <h2>How It Works</h2>
    <p>The robot receives voice commands via an Android app, which transmits signals through Bluetooth (HC-06 module). The Arduino processes the signals and controls the motors accordingly.</p>
    
    <h2>Key Process Flow</h2>
    <ol>
        <li>Voice command is given via an Android app.</li>
        <li>The Bluetooth module receives and transmits the command to the Arduino Uno.</li>
        <li>The Arduino interprets the command and controls the motors via the L293D motor driver.</li>
        <li>The LCD screen displays the current command.</li>
        <li>The robot executes the movement as per the given instruction.</li>
    </ol>
    
    <h2>Why This Project Matters for the Future?</h2>
    <p>With increasing automation in daily life, voice-controlled robots could revolutionize home assistance, education, and entertainment. Eleta serves as an accessible introduction to AI-driven robotics.</p>
    
    <h2>Future Enhancements</h2>
    <ul>
        <li>Integration with IoT for remote control.</li>
        <li>AI-based speech recognition for enhanced accuracy.</li>
        <li>Obstacle detection using ultrasonic sensors.</li>
        <li>Mobile app enhancements with customizable commands.</li>
    </ul>
    
    <h2>Project Components</h2>
    <ul>
        <li>Arduino Uno</li>
        <li>L293D Motor Driver Shield</li>
        <li>HC-06 Bluetooth Module</li>
        <li>4 x DC Gear Motors with Wheels</li>
        <li>16x2 LCD Display with I2C</li>
        <li>Battery Pack</li>
        <li>Jumper Wires</li>
    </ul>
    
    <h2>Arduino Code</h2>
    <pre>
        // Arduino code goes here
    </pre>
    
    <h2>Project Outcomes</h2>
    <p>The project successfully demonstrates a responsive and interactive robot that follows voice commands. It showcases the seamless integration of hardware and software for intuitive control.</p>
    
    <h2>Project Demos</h2>
    <p>Check out the live demonstration of Eleta in action! [Insert Video or GIF]</p>
    
    <h2>Contribution & Support</h2>
    <p>We welcome contributions! Feel free to fork this project, improve its functionality, or propose new features. If you found this useful, give it a ⭐ on GitHub!</p>
</body>
</html>
