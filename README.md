Light Sensor Project with Arduino Nano, OLED, and LDR
Project Overview
This project demonstrates how to build a digital light intensity meter using an Arduino Nano, an LDR (Light Dependent Resistor) module, and an OLED display. The system reads ambient light levels, processes the analog signal, and displays the results in real-time on a small screen. This is an excellent beginner-to-intermediate electronics project that introduces concepts like analog-to-digital conversion, sensor interfacing, and graphical display programming.

Project Components
Hardware Components
Component	Purpose	Specifications
Arduino Nano	Main microcontroller	ATmega328P, 5V operating voltage
LDR Module (3-pin)	Light sensing element	Analog output, 0-5V range
OLED Display	Visual output	128x64 pixels, I2C interface
Jumper Wires	Electrical connections	Male-to-female, male-to-male
Breadboard	Prototyping platform	400 or 830 tie-points
Software Requirements
Arduino IDE (latest version)

Adafruit SSD1306 Library

Adafruit GFX Library

Wire Library (built-in)

Signal Flow
Light Detection: LDR module converts light intensity to voltage

Analog-to-Digital Conversion: Arduino's ADC converts voltage to digital value (0-1023)

Data Processing: Microcontroller scales and formats the reading

Display Output: OLED screen shows the processed light value

Circuit Diagram
Complete Wiring Schematic
text
Arduino Nano          LDR Module          OLED Display
─────────────        ───────────         ────────────
   5V      ────────── VCC                 VCC
   GND     ────────── GND                 GND
   A0      ────────── AO                  (NC)
   A4 (SDA)────────── (NC)                SDA
   A5 (SCL)────────── (NC)                SCL
Detailed Connection Guide
Arduino Nano Pin	Connected To	Wire Color (Typical)
5V	LDR VCC	Red
5V	OLED VCC	Red
GND	LDR GND	Black
GND	OLED GND	Black
A0	LDR AO	Yellow
A4 (SDA)	OLED SDA	Blue
A5 (SCL)	OLED SCL	Green
Important Notes:
I2C Communication: The OLED uses the I2C protocol, which requires only two data lines (SDA and SCL) in addition to power and ground

Pull-up Resistors: The LDR module already includes a built-in 10kΩ pull-up resistor (for pull-up configuration) or pull-down resistor (for pull-down configuration)

Shared Bus: Both devices are powered from the Nano's 5V pin, but the LDR's analog output goes to a separate pin (A0)



