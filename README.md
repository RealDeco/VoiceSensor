
# 🎙️ VoiceSensor

**A compact 3-in-1 device combining a Voice Assistant, Presence Sensor, and Ambient Light Sensor for Home Assistant — or an “Ear-Only” setup without additional sensors.**

---

## 📄 Versions

### **`VoiceSensorOLD.yaml` (SuperMini)**

An older project from a couple of years back.

* Very simple YAML, but *still works amazingly well*.
* **No MicroWakeWord** (SuperMini has no PSRAM).
* **No timer functionality** included in the code.

---

### **`VoiceSensor.yaml` (ESP32-S3 Zero)**

The new recommended version.

* Works **only** with **ESP32-S3 Zero** (not SuperMini).
* Zero includes **2MB PSRAM**, required for on-device MicroWakeWord.
* Supports **up to 2 wake words**, processed locally.
* For outputting responses to an external media player, see: **[tts_uri.md](tts_uri.md)**.

---

## 📸 Images

<p align="center">
  <img src="https://github.com/user-attachments/assets/06bbc9ff-7d2f-4aa9-9395-547f1c3b3554" width="45%" />
  <img src="https://github.com/user-attachments/assets/fc48c042-4793-42a2-abfb-77fd1b28759b" width="45%" />
</p>

<p align="center">
  <img src="https://github.com/user-attachments/assets/f8d948ec-b0d3-48a9-a342-1229470f3cdc" width="45%" />
  <img src="https://github.com/user-attachments/assets/31278801-e4c6-4113-9ea9-fc64fe5d37d4" width="45%" />
</p>

<p align="center">
  <img src="https://github.com/user-attachments/assets/094d0237-6862-4682-ab70-27baab721618" width="45%" />
  <img src="https://github.com/user-attachments/assets/7a953ff4-168c-42d4-afb0-72a4bac22e5e" width="45%" />
</p>

<p align="center">
  <img src="https://github.com/user-attachments/assets/c0871b54-cf89-4bdd-9b51-5e7f91af2e9b" width="45%" />
</p>


## 🛠️ Parts List

### **VoiceSensor Setup (Full Device)**

* **ESP32-S3 Zero**
* **INMP441 microphone**
* **LD2410C presence sensor**
* **BH1750 ambient light sensor**
* **16mm push button** (GPIO 10)

### **Ear-Only Setup (No Sensors)**

* **ESP32-S3 Zero**
* **INMP441 microphone**

---

## 📦 Assembly Notes

* Designed to fit inside a custom enclosure with accessible test pins.
* **Minimal soldering required**, unless:

  * You need custom power splitters.
  * Pin headers arrive loose or unsoldered.

---

## ✨ Features

* 🗣️ **Local Voice Assistant**
  On-device processing with LED phase feedback.

* 👤 **Presence Detection**
  LD2410C millimeter-wave radar sensor.

* 💡 **Light Level Monitoring**
  BH1750 digital luminance sensor.

* 🔘 **Push Button Input**
  For triggering actions manually.

* 🔧 **Maker-Friendly**
  Fully testable on a breadboard before final assembly.

---

