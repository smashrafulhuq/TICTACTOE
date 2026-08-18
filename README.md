# 🎮 Arduino Tic-Tac-Toe (Embedded Systems Approach)

A resource-efficient, standalone Tic-Tac-Toe game implemented on the **ATmega328P (Arduino Uno)** microcontroller. The system interfaces with an **I2C SSD1306 OLED display** for visual feedback and a **4x4 matrix keypad** for user input.

---

## 📌 Features

* **Hardware Multiplexing:** Utilizes row-column scanning across 8 digital I/O pins to read 16 keypad inputs efficiently.
* **I2C Protocol Display:** Saves GPIO pins by driving a 128x64 OLED display using only 2 TWI lines (`SDA` / `SCL`).
* **UI Color Segmentation:** Optimizes the physical yellow (top 16px) and blue (bottom 48px) zones for status bar and game board separation.
* **O(1) Win Detection:** Constant-time game state and win evaluation across 8 vectors (3 rows, 3 columns, 2 diagonals).
* **Direct Input Mapping:** Mathematical coordinate mapping reduces branch overhead and switch-case complexity.
* **Memory Safety:** Employs strictly static memory allocation to prevent heap fragmentation on constrained hardware.

---

## 🛠️ Hardware Requirements

* **Microcontroller:** Arduino Uno Rev3 (ATmega328P)
* **Display:** 0.96" I2C SSD1306 OLED (128x64 pixels, Address: `0x3C`)
* **Input Device:** 4x4 Membrane Keypad
* **Accessories:** Breadboard, Jumper wires, USB cable

---

## 🔌 Pin Mapping

### 1. SSD1306 OLED Display (I2C)
| OLED Pin | Arduino Uno Pin | Description |
| :--- | :--- | :--- |
| **VCC** | 5V / 3.3V | Power Supply |
| **GND** | GND | Ground |
| **SDA** | **A4** | I2C Serial Data |
| **SCL** | **A5** | I2C Serial Clock |

### 2. 4x4 Matrix Keypad
| Matrix Pin | Arduino Uno Pin | Function |
| :--- | :--- | :--- |
| **Row 1** | **D9** | Output Scan |
| **Row 2** | **D8** | Output Scan |
| **Row 3** | **D7** | Output Scan |
| **Row 4** | **D6** | Output Scan |
| **Col 1** | **D5** | Input with Pull-up |
| **Col 2** | **D10** | Input with Pull-up (Replaced faulty pin D4) |
| **Col 3** | **D3** | Input with Pull-up |
| **Col 4** | **D2** | Input with Pull-up |

---

## 🕹️ Controls & Gameplay

| Key | Action |
| :--- | :--- |
| **1 – 9** | Place **X** or **O** in corresponding grid cell (1 = Top-Left, 9 = Bottom-Right) |
| **D** | **Global Reset** button to restart the game at any time |
| **Any Key** | Reset/restart after a win or draw condition |

---

## 💻 Software Dependencies

To compile and upload the firmware, ensure the following libraries are installed in the Arduino IDE:
* [Adafruit GFX Library](https://github.com/adafruit/Adafruit-GFX-Library)
* [Adafruit SSD1306 Library](https://github.com/adafruit/Adafruit_SSD1306)
* [Keypad Library by Mark Stanley / Brevig](https://playground.arduino.cc/)

---

## 👥 Authors

* **S M Ashraful Huq**  — Dept. of CSE, BRAC University
* **Mohammad Mutoasituzzaman**  — Dept. of CSE, BRAC University
* **Md Samsul Huda**  — Dept. of CSE, BRAC University
* **Tarannum Al Akida**  — Dept. of CSE, BRAC University

---

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
