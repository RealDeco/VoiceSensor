
# 🎙️ VoiceSensor & VoiceEar

why should a voice assistant device be 1 device when it could be 3? or why should sensors be 3 devices when they could be 1?

A compact 3-in-1 device combining a Voice Assistant, Presence Sensor, and Ambient Light Sensor for Home Assistant

— or an “Ear-Only” setup without additional sensors using other devices for display and audio.

---

<p align="center">
  <img src="https://github.com/user-attachments/assets/802fff0f-d109-4112-8e00-402f8a40eb36" width="45%" />
  <img src="https://github.com/user-attachments/assets/13dd2121-11b5-4d81-a2b5-1f88549423ca" width="45%" />
</p>

<p align="center">
  <img src="https://github.com/user-attachments/assets/ee319024-1b9b-4d8f-b06a-33ce94c58ba0" width="45%" />
  <img src="https://github.com/user-attachments/assets/b88e244e-7289-4f8b-a344-693752ce39c8" width="45%" />

  
  <img src="https://github.com/user-attachments/assets/31278801-e4c6-4113-9ea9-fc64fe5d37d4" width="45%" />
</p>

<p align="center">
  <img src="https://github.com/user-attachments/assets/f8d948ec-b0d3-48a9-a342-1229470f3cdc" width="45%" />
  <img src="https://github.com/user-attachments/assets/fc48c042-4793-42a2-abfb-77fd1b28759b" width="45%" />
</p>

<p align="center">
  <img src="https://github.com/user-attachments/assets/06bbc9ff-7d2f-4aa9-9395-547f1c3b3554" width="45%" />
  <img src="https://github.com/user-attachments/assets/7a953ff4-168c-42d4-afb0-72a4bac22e5e" width="45%" />
</p>

---

## 📄 Files

### **`VoiceSensorOLD.yaml` (SuperMini)**

An older project from a couple of years back.

* Very simple YAML, but *still works amazingly well*.
* **No MicroWakeWord** (supports SuperMini that has no PSRAM).
* **No timer functionality** included in the code.

---

### **`VoiceSensorNEW.yaml` (ESP32-S3 Zero + inmp441 mic + ld2410c presence sensor + bm1750 light sensor)**

* Works **only** with **ESP32-S3 Zero** (not SuperMini).
* Zero includes **2MB PSRAM**, required for on-device MicroWakeWord.
* Supports **up to 2 wake words**, processed locally.
* For outputting responses to an external media player, see: **[tts_uri.md](tts_uri.md)**

---

### **`VoiceEar.yaml` (ESP32-S3 Zero + inmp441 mic, no sensors)**

* Just the "Ear" (no sensors) version of "VoiceSensor"

---

### **`VoiceSensorScreen.yaml` (Guition 4" 4848S040 with no mic)**

* Simple yaml that reads the phase id's from HA and display images accordingly
* Can also control the "virtual touch" of the voicesensor by touching the display.

---

### **`CustomButton.md`**

* Display the phase id images on your Dashboard

---

### **`request_response_to_dashboard_automation.yaml`** and
### **`request_response_to_dashboard_card.md`**

* show request and response text on dashboard

---

### **`tts_uri.md`**

* How to pass audio to another mediaplayer.

---

### **`multisensorcase.3mf`**

* 3D file for VoiceSensor Case
* 
---

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

