# Project 1: LED Blink & Fade

## Overview
This project serves as the "Hello, World!" of physical computing. It covers the most fundamental concepts of digital output and Pulse Width Modulation (PWM) by controlling a single LED.

The `.ino` file contains two main functions:
1.  A standard blinking sequence using `digitalWrite()`.
2.  A smooth "breathing" or fading effect using `analogWrite()`.

## Components Required
*   1x Arduino UNO
*   1x LED (any color)
*   1x 220Ω Resistor
*   1x Breadboard
*   Jumper Wires

## Circuit Diagram
The circuit is straightforward, connecting the LED to a digital pin on the Arduino through a current-limiting resistor.

*   Connect the **Arduino's GND pin** to the negative rail of the breadboard.
*   Connect the **LED's shorter leg (cathode)** to the negative rail.
*   Connect the **LED's longer leg (anode)** to one end of the 220Ω resistor.
*   Connect the other end of the resistor to **Arduino Digital Pin ~9**. (Using a PWM-capable pin, marked with '~', is essential for the fade effect).

## Key Concepts
*   **`pinMode(pin, OUTPUT)`:** Configures a specific pin to behave as an output.
*   **`digitalWrite(pin, HIGH/LOW)`:** Sets the output pin to either 5V (HIGH) or 0V (LOW), turning the LED on or off.
*   **`analogWrite(pin, value)`:** Simulates an analog output using PWM. The `value` can range from 0 (fully off) to 255 (fully on), allowing for variable brightness levels.
*   **`delay(milliseconds)`:** Pauses the program for a specified duration, which is crucial for controlling the timing of the blink.