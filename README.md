# RustInSynthPCB

A standalone ESP32-S3 synthesizer mainboard: a carrier PCB hosting a DevKitC-1-N16R8 module on the back face, with OLED, 4 pots, 4 buttons, rotary encoder, stereo audio ADC/DAC (PCM1860 + PCM5102A), four 6.35mm jacks, DIN-5 MIDI input, microSD and USB — designed in **KiCad 10.0**.

## 🛠 Features
* **MCU:** ESP32-S3 (Dual-core @ 240MHz)
* **Memory:** 16MB Flash / 8MB Octal PSRAM (N16R8 variant)
* **Connectivity:**
    * **USB-C (UART):** Dedicated interface for programming and debugging.
    * **USB-C (Native):** Direct access to S3 USB OTG pins.
* **I/O:** Full breakout of all usable GPIOs to 0.1" (2.54mm) headers.
* **Design Tool:** KiCad 9.0

## ⚙️ Hardware Setup
To utilize the 16MB Flash and 8MB PSRAM in your IDE (Arduino/ESP-IDF), use the following settings:

| Setting | Value |
| :--- | :--- |
| **Board** | ESP32S3 Dev Module |
| **Flash Mode** | QIO |
| **Flash Size** | 16MB |
| **PSRAM** | OPI PSRAM |

<img width="1723" height="1012" alt="image" src="https://github.com/user-attachments/assets/859842eb-6d3d-4e1b-95d7-e6d1da4eae34" />


## 📦 Production Files
This repository includes production-ready files optimized for manufacturing via **JLCPCB**, located in the `/JLCPCB BOM & Gerber Files` folder. This includes:
* Gerber Files
* Drill Files
* BOM (Bill of Materials)
* CPL (Component Placement List / Pick-and-Place)

---
*Note: This project is shared for reference and educational purposes.*
