# IOT-based-smart-lighting-system
# 🌃 Smart Urban Lighting System – IoT-Based Energy Management

An intelligent street lighting solution powered by IoT that dynamically adjusts brightness based on ambient light and human presence, significantly improving energy efficiency in urban areas.

---

## 📌 Project Overview

Traditional street lights operate on static schedules, causing energy wastage and limited control. This project introduces a smart system using sensors and microcontrollers to automate and optimize lighting based on environmental conditions and pedestrian motion.

---

## 🚀 Features

- ✅ Motion-based LED control
- ✅ Ambient light sensing (LDR)
- ✅ Adaptive brightness using PWM
- ✅ Energy-saving dimming during inactivity
- ✅ Real-time data logging and cloud dashboard (optional)
- ✅ Expandable to LoRa/Zigbee communication

---

## 🛠️ Tech Stack

| Component        | Description                                      |
|------------------|--------------------------------------------------|
| **Arduino Uno**  | Central microcontroller                          |
| **PIR Sensor**   | Motion detection                                 |
| **LDR Sensor**   | Ambient light measurement                        |
| **LED/Streetlight** | PWM controlled brightness                     |
| **LoRa/Zigbee** *(optional)* | Wireless communication               |
| **Cloud Platform** *(optional)* | ThingsBoard / Blynk / Firebase    |

---

## 🔌 Circuit Connections

| Sensor/Device  | Arduino Pin |
|----------------|-------------|
| LDR            | A0          |
| PIR Sensor     | D2          |
| LED (PWM)      | D9          |
| LoRa TX/RX     | D10/D11 *(via SoftwareSerial)* |

---

## 💡 Automation Logic

| Condition                          | Action              |
|------------------------------------|---------------------|
| Night + Motion Detected            | Bright Light (100%) |
| Night + No Motion                  | Dim Light (30%)     |
| Daytime                            | Lights OFF          |

---

## 🔁 Sample Sensor Data

| Time      | Light (Lux) | Motion | Brightness (%) |
|-----------|-------------|--------|----------------|
| 06:15 PM  | 80          | Yes    | 100            |
| 06:30 PM  | 60          | No     | 30             |
| 07:45 PM  | 0           | Yes    | 100            |

---



