<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Eleta – A Voice-Controlled Smart Robot</title>
</head>
<body>
    <h1>Eleta – A Voice-Controlled Smart Robot 🤖</h1>
    
    <h2>Subtitle</h2>
    <p>An innovative voice-controlled robot designed for seamless human interaction and automation.</p>
    
    <h2>The Problem</h2>
    <p>Traditional robots rely on manual controls, making human-machine interaction complex and less intuitive. Voice commands simplify this process, enhancing usability.</p>
    
    <h2>The Smart Solution</h2>
    <p>Eleta is a smart robot that listens to voice commands and executes movements such as moving forward, backward, turning, and even performing dances.</p>
    
    <h2>Features</h2>
    <ul>
        <li>Voice Control via Bluetooth</li>
        <li>Predefined Movement Patterns</li>
        <li>Real-time Response</li>
        <li>Customizable Commands</li>
        <li>Interactive LED Display</li>
    </ul>
    
    <h2>How It Works</h2>
    <p>Using an Arduino Uno, Bluetooth module, and motor driver shield, Eleta receives voice commands via an Android phone, translating them into motion.</p>
    
    <h2>Key Process Flow</h2>
    <ol>
        <li>User gives a voice command through the Android app.</li>
        <li>The Bluetooth module sends the command to the Arduino.</li>
        <li>The Arduino processes the command and activates the motors.</li>
        <li>The robot executes the corresponding action.</li>
    </ol>
    
    <h2>Why This Project Matters for the Future?</h2>
    <p>With AI and IoT integration, voice-controlled robotics can play a major role in assistive technology, automation, and smart home applications.</p>
    
    <h2>Future Enhancements</h2>
    <ul>
        <li>Obstacle Avoidance with Ultrasonic Sensors</li>
        <li>IoT Connectivity for Remote Access</li>
        <li>Advanced AI for Improved Voice Recognition</li>
        <li>Integration with Home Automation Systems</li>
    </ul>
    
    <h2>Project Components</h2>
    <ul>
        <li>Arduino Uno</li>
        <li>L293D Motor Driver Shield</li>
        <li>HC-06 Bluetooth Module</li>
        <li>4 x DC Gear Motors with Wheels</li>
        <li>LCD Display (I2C)</li>
        <li>Power Supply (Battery Pack)</li>
        <li>Wires and Connectors</li>
    </ul>
    
    <h2>Arduino Code</h2>
    <pre>
        // Include necessary libraries and define motor pins
        #include &lt;Wire.h&gt;
        #include &lt;LiquidCrystal_I2C.h&gt;
        LiquidCrystal_I2C lcd(0x27, 16, 2);
        ... (Arduino code here) ...
    </pre>
    
    <h2>Project Outcomes</h2>
    <p>A functional voice-controlled robot capable of executing commands seamlessly, demonstrating the potential for smart automation.</p>
    
    <h2>Project Demos</h2>
    <p>Check out the demo video here: <a href="#">[Insert Video Link]</a></p>
    
    <h2>Contribution & Support</h2>
    <p>Want to contribute? Fork this repository, create pull requests, or reach out for collaboration!</p>
</body>
</html>
