<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Eleta - Voice Controlled Robot</title>
    <style>
        body { font-family: Arial, sans-serif; line-height: 1.6; margin: 20px; padding: 20px; }
        h1, h2, h3 { color: #333; }
        ul { margin-left: 20px; }
    </style>
</head>
<body>
    <h1>Eleta - Voice Controlled Robot</h1>
    
    <h2>Objective</h2>
    <p>The goal of this project is to develop a voice-controlled robot that can respond to specific spoken commands via a Bluetooth-connected Android device. The robot should be able to execute various movements, including directional navigation, predefined geometric patterns, and fun dance motions. This project aims to enhance human-robot interaction and serve as an educational tool for embedded systems and robotics.</p>
    
    <h2>Method</h2>
    <p>The robot is built using an Arduino/ESP32 microcontroller, an HC-06 Bluetooth module, and an L298N motor driver to control two DC motors. A 16x2 LCD display provides feedback on the received commands. The system is programmed to recognize specific voice inputs from an Android app, which are then processed by the microcontroller to drive the motors accordingly. The design allows for future expansions, such as adding obstacle detection sensors and IoT features.</p>
    
    <h2>Outcome</h2>
    <p>The final result is a fully functional voice-controlled robot capable of responding to various commands such as moving forward, backward, turning, making shapes, and performing a dance routine. The robot demonstrates reliable Bluetooth communication, smooth motor control, and an intuitive user interface through an Android application. This project provides hands-on experience in embedded systems, motor control, and wireless communication while making robotics more interactive and engaging.</p>
    
    <h2>Component List</h2>
    <ul>
        <li><strong>Microcontroller:</strong> Arduino Uno/ESP32</li>
        <li><strong>Motor Driver Module:</strong> L298N Motor Driver</li>
        <li><strong>Motors:</strong> 2 DC Motors</li>
        <li><strong>Bluetooth Module:</strong> HC-05 or HC-06</li>
        <li><strong>LCD Display:</strong> 16x2 I2C LCD Display</li>
        <li><strong>Power Supply:</strong> 9V Battery or Rechargeable Battery Pack</li>
        <li><strong>Chassis:</strong> 2-Wheel Robot Chassis with Caster Wheel</li>
        <li><strong>Wires and Connectors:</strong> Jumper Wires, Screw Terminals</li>
        <li><strong>Resistors:</strong> 10kΩ Resistor</li>
        <li><strong>Potentiometer:</strong> For LCD contrast adjustment</li>
        <li><strong>Miscellaneous:</strong> ON/OFF Switch, Breadboard, Mounting Screws</li>
        <li><strong>Tools:</strong> Soldering Iron, Screwdriver, Multimeter</li>
    </ul>
    
    <h2>How It Works</h2>
    <p>The Android app sends voice commands via Bluetooth to the HC-06 module, which is connected to the microcontroller. The microcontroller processes the command and controls the L298N motor driver to move the motors accordingly. The LCD screen displays the received command for user feedback. The modular design allows for future upgrades, such as obstacle detection and IoT integration.</p>
</body>
</html>
