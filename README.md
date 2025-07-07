# BlueFi Shield

**Bluetooth + Wi-Fi Arduino Shield using ESP32**

[![View on OSHWLab](https://img.shields.io/badge/View%20on-OSHWLab-blue?logo=oshwlab&style=flat-square)](https://oshwlab.com/devaansh/arduino-shield)

---

## 🧠 Overview

**BlueFi Shield** is a custom-designed, open-source Arduino-compatible shield that adds both **Bluetooth** and **Wi-Fi** capabilities to any standard Arduino board using the powerful **ESP32-WROOM-32E** module.

Built for flexibility, BlueFi can act as:
- A **wireless co-processor** via UART (ESP32 <–> Arduino)
- A **standalone ESP32 dev board** via jumper wiring
- A **Bluetooth bridge**, **NeoPixel controller**, or **wireless debug interface**

Designed in **EasyEDA Pro**, this board follows all JLCPCB Economic PCBA rules and is fully open source.

---

## 📦 Features

- ✅ **ESP32-WROOM-32E** (Wi-Fi + Bluetooth Classic + BLE)
- ✅ UART interface with level-shifted TX for Arduino compatibility
- ✅ BOOT and RESET buttons (IO0 and EN support)
- ✅ Onboard **NeoPixel pad** (1x WS2812B 5050, optional)
- ✅ Exposed **touch pad (GPIO4 / T0)** for gesture input
- ✅ Voltage regulator (AMS1117-3.3) with proper decoupling
- ✅ All basic parts — JLCPCB Economic Assembly compatible
- ✅ ASCII art + labeled silkscreen for fun + usability

---

## 📂 Files Included

| File                      | Description                                 |
|---------------------------|---------------------------------------------|
| `Gerbers.zip` | Gerber files for fabrication               |
| `BOM.xlsx` | Bill of Materials (JLCPCB Basic)         |
| `PickAndPlace.xlsx` | Pick and Place / CPL file for assembly  |

---

## 📎 OSHWLab Project

🔗 View full schematic and PCB layout:  
👉 **[BlueFi Shield on OSHWLab →](https://oshwlab.com/devaansh/arduino-shield)**

---

## 🚀 How to Use

### UART Shield Mode:
- Connect `D2 (TX)` and `D3 (RX)` from Arduino to the shield’s UART header
- Use `IO0` button + `EN` to enter bootloader if flashing via Arduino serial

### Standalone ESP32 Mode:
- Supply 5V via VIN or USB power
- Use ESP32 as the main MCU

### Touch Input:
- Touch the exposed `T0` pad to trigger actions (capacitive sensing)

---

## ⚙️ Software Example

```cpp
#define TOUCH_PIN T0
#define LED_PIN 14

void setup() {
  Serial.begin(115200);
  pinMode(LED_PIN, OUTPUT);
}

void loop() {
  if (touchRead(TOUCH_PIN) < 40) {
    digitalWrite(LED_PIN, HIGH);
  } else {
    digitalWrite(LED_PIN, LOW);
  }
}
````

---

## 📄 License

This project is open-source under the **MIT License**.
Contributions and forks welcome!

---

## 🛠️ Made with ❤️ by [@devaansh](https://oshwlab.com/devaansh)
