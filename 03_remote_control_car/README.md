# Project 3: Two-Wheeled Remotely Controlled Car

## Overview
This project integrates multiple components to build a functional mobile robot platform. It focuses on motor control using the L298N driver and implements a simple remote control system via the Arduino's serial port. The user can send commands from a computer to control the car's movement.

## Components Required
*   1x Arduino UNO
*   1x Two-Wheeled Robot Chassis Kit (includes 2x DC motors, wheels, chassis)
*   1x L298N Motor Driver Module
*   1x Battery Pack (e.g., 4x AA batteries, providing 6V)
*   Jumper Wires (Male-to-Female and Male-to-Male)

## Circuit Diagram
Wiring is critical for this project. Ensure connections are secure.

*   **Power Connections:**
    *   Connect the battery pack's positive (+) terminal to the **L298N's VCC (or 12V) pin**.
    *   Connect the battery pack's negative (-) terminal to the **L298N's GND pin**.
    *   Connect the **L298N's GND pin** to one of the **Arduino's GND pins** to create a common ground.

*   **Motor Connections:**
    *   Connect the Left Motor to the **L298N's OUT1 and OUT2** terminals.
    *   Connect the Right Motor to the **L298N's OUT3 and OUT4** terminals.

*   **Control Signal Connections (L298N to Arduino):**
    *   L298N **ENA** -> Arduino Pin **~5** (PWM for Left Motor Speed)
    *   L298N **IN1** -> Arduino Pin **7**
    *   L298N **IN2** -> Arduino Pin **8**
    *   L298N **IN3** -> Arduino Pin **9**
    *   L298N **IN4** -> Arduino Pin **10**
    *   L298N **ENB** -> Arduino Pin **~6** (PWM for Right Motor Speed)
    *   *(Note: The L298N's 5V pin can often be left disconnected unless you are powering the Arduino from it, which is not recommended with standard AA batteries).*

## Key Concepts
*   **H-Bridge (L298N):** A circuit that allows a voltage to be applied across a load in either direction. This is how we control the direction of the DC motors.
*   **Motor Control Logic:**
    *   **Forward:** IN1=HIGH, IN2=LOW
    *   **Backward:** IN1=LOW, IN2=HIGH
    *   **Stop/Brake:** IN1=LOW, IN2=LOW
*   **Speed Control (PWM):** Using `analogWrite()` on the ENA and ENB pins allows for variable motor speed. A value of 0 is stopped, and 255 is maximum speed.
*   **Serial Communication:** The code uses `Serial.available()` to check if the computer has sent data and `Serial.read()` to read the character command (e.g., 'w' for forward, 's' for backward).
*   **Function Abstraction:** The code is structured with functions like `goForward()`, `turnLeft()`, `stopMotors()` to make the main loop clean and readable.