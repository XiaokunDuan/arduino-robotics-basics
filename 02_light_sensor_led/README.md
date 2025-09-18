# Project 2: Sensor-Controlled LED (Automatic Light)

## Overview
This project introduces the concept of sensor input. It demonstrates a fundamental robotics loop: **sense -> think -> act**. The Arduino reads ambient light levels from a photoresistor and makes a decision to turn an LED on or off based on that data.

## Components Required
*   1x Arduino UNO
*   1x LED
*   1x 220Ω Resistor (for LED)
*   1x Photoresistor (LDR)
*   1x 10kΩ Resistor (for the voltage divider)
*   1x Breadboard
*   Jumper Wires

## Circuit Diagram
This circuit combines the previous LED setup with a new voltage divider circuit for the photoresistor.

1.  **LED Circuit:**
    *   Connect the LED and its 220Ω resistor to **Digital Pin ~9** and **GND**, as in the previous project.

2.  **Photoresistor Circuit (Voltage Divider):**
    *   Connect one leg of the photoresistor to the **Arduino's 5V pin**.
    *   Connect the other leg of the photoresistor to **Arduino Analog Pin A0**.
    *   From that same point (Pin A0), connect the 10kΩ resistor to the **Arduino's GND pin**. This creates a voltage divider, where the voltage at A0 changes based on the light hitting the photoresistor.

## Key Concepts
*   **`pinMode(pin, INPUT)`:** Configures a pin to read data from a sensor. For analog pins, this is the default and often not explicitly required.
*   **`analogRead(pin)`:** Reads the voltage from a specified analog input pin (A0-A5) and returns a value between 0 (0V) and 1023 (5V).
*   **Voltage Divider:** A fundamental circuit used to convert a variable resistance (from the photoresistor) into a variable voltage that the Arduino can measure.
*   **`Serial.begin(9600)` and `Serial.println(value)`:** Essential for debugging. This allows the Arduino to send the sensor readings back to the computer, so you can see the values and set an appropriate threshold in your code.
*   **Conditional Logic (`if/else`)**: Used to make a decision based on the sensor reading (e.g., `if (lightValue < 300) { turn LED on; }`).