
<p align="center">
  <img src="https://github.com/user-attachments/assets/802fff0f-d109-4112-8e00-402f8a40eb36" width="45%" />
  <img src="https://github.com/user-attachments/assets/13dd2121-11b5-4d81-a2b5-1f88549423ca" width="45%" />
</p>

# 🎙️ VoiceSensor • VoiceEar • VoiceScreen

## Overview

For years, I’ve been advocating for **speakerless voice assistants** — mainly because 99% of us already have a media player in our homes, right?

This project contains three companion devices designed to work with Home Assistant and ESPHome: **VoiceSensor**, **VoiceEar**, and **VoiceScreen**.

---

## 🟦 VoiceSensor

The original prototype of this project (and the name of this repo).

It was a single device containing:

* a microphone
* a presence sensor
* a light sensor

The idea: these sensors naturally belong together and are usually mounted in the same place — high on a wall or ceiling.

---

## 🟩 VoiceEar ( the $4 VA :)

A simpler version of VoiceSensor.
It contains **only a microphone**, acting purely as an “ear” for your voice assistant.

Audio responses can be sent to **any Home Assistant media player**, so the device itself does not need a speaker.

---

## 📡 Event Outputs

All devices — VoiceSensor, VoiceEar, Respeaker Lite, and the entire Xiaozhi-ESPHome lineup — send the following events:

* **Audio Path**
  Used to route the assistant’s audio output to any chosen media player via automation.

* **Request Text**
  The recognized speech (what the user asked).
  Can be forwarded to VoiceScreen or a dashboard.

* **Response Text**
  The assistant’s reply in text form.
  Also sendable to VoiceScreen or dashboards.

* **Phase ID**
  The current pipeline step.
  Useful for showing different visuals on VoiceScreen depending on the assistant’s state.

---

## 🖥️ VoiceScreen

VoiceScreen is an ESP32-S3 display that acts as a **visual companion** to VoiceSensor, VoiceEar, and all devices from the Xiaozhi-ESPHome repository.

It waits for incoming events and updates the display accordingly.
Touching the screen sends button events back to the selected voice assistant device (e.g., Start / Stop listening).

---

<p align="center">


## 🟦 VoiceSensor DIY images
  
  <img src="https://github.com/user-attachments/assets/31278801-e4c6-4113-9ea9-fc64fe5d37d4" width="45%" />
  <img src="https://github.com/user-attachments/assets/f8d948ec-b0d3-48a9-a342-1229470f3cdc" width="45%" />
</p>

<p align="center">
  <img src="https://github.com/user-attachments/assets/06bbc9ff-7d2f-4aa9-9395-547f1c3b3554" width="45%" />
  <img src="https://github.com/user-attachments/assets/7a953ff4-168c-42d4-afb0-72a4bac22e5e" width="45%" />
</p>

## 🟩 VoiceEar DIY images

<p align="center">
  <img src="https://github.com/user-attachments/assets/64c078f4-0591-42e3-9cb2-cb7ef6e50c4c" width="45%" />
  <img src="https://github.com/user-attachments/assets/c5962f42-a8f1-4350-b4e6-79be4bafe545" width="45%" />
  <img src="https://github.com/user-attachments/assets/5a598133-c7a6-4f57-8aeb-2022d6cd9706" width="45%" />
  <img src="https://github.com/user-attachments/assets/7ef6d772-2f51-43ef-a1bd-8c7ffb9a86cb" width="45%" />

Schematics

  <img src="https://github.com/user-attachments/assets/ee319024-1b9b-4d8f-b06a-33ce94c58ba0" width="45%" />
  <img src="https://github.com/user-attachments/assets/b88e244e-7289-4f8b-a344-693752ce39c8" width="45%" />
</p>


---

## 📄 Files

### **`VoiceSensor.yaml` (ESP32-S3 Zero + inmp441 mic + ld2410c presence sensor + bm1750 light sensor)**

* Works **only** with **ESP32-S3 Zero** (not SuperMini).
* Zero includes **2MB PSRAM**, required for on-device MicroWakeWord.
* Supports **up to 2 wake words**, processed locally.
* For outputting responses to an external media player, see: **[tts_uri.md](tts_uri.md)**

---

### **`VoiceEar.yaml` (ESP32-S3 Zero + inmp441 mic, no sensors)**

* Just the "Ear" (no sensors) version of "VoiceSensor"

---

### **`respeaker-satellite-base.yaml` custom version of the  official Respeaker-Lite-ESPHome-integration**

* Use the original placement of the file (esphome/common/)

---

### **`VoiceScreen.yaml` (Guition 4" 4848S040 with no mic.)**

* Simple yaml that reads the phase id's from HA and display images accordingly
* Can also control the "virtual touch" of the voicesensor by touching the display.

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

## 📦 Assembly Notes (VoiceSensor)

* Designed to fit inside a custom enclosure with accessible test pins.
* **Minimal soldering required**, unless:

  * You need custom power splitters.
  * Pin headers arrive loose or unsoldered.

---

## ✨ Features (Voicesensor)

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

