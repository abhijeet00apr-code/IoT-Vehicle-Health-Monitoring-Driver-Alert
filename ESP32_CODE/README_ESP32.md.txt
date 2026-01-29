# ESP32 Firmware – CAN to IoT Gateway

## 📌 Overview
This folder contains the firmware for the **ESP32**, which acts as the **gateway layer** in the IoT-based Vehicle Health Monitoring and Driver Alert System.

The ESP32 receives real-time data from STM32 over the **CAN bus**, displays it locally on a TFT/LCD, and forwards the data securely to the cloud using **MQTT over Wi-Fi**.

---

## 🎯 Responsibilities of ESP32
- Receive CAN data frames from STM32
- Parse and process sensor data
- Display real-time values on TFT/LCD
- Publish data to AWS IoT using MQTT
- Monitor communication health and detect CAN failures

---

## 🔗 CAN Communication
- CAN Interface: ESP32 TWAI (CAN) driver
- Baud Rate: `500 kbps`
- CAN ID Filter: `0x123`
- Receives:
  - Temperature
  - Oil level
  - Vibration data
  - Driver touch status

---

## 📡 Wi-Fi & Cloud Connectivity
- Wi-Fi Standard: IEEE 802.11 b/g/n (2.4 GHz)
- Protocol: MQTT over TLS
- Cloud Platform: **AWS IoT Core**
- Port: `8883` (Secure MQTT)

---

## ☁️ Cloud Integration
- Publishes sensor data in **JSON format**
- AWS IoT rules configured for:
  - Threshold detection
  - CloudWatch monitoring
- **AWS SNS** used to send real-time email alerts during abnormal conditions

---

## 📺 Local Display
- Real-time system parameters displayed on TFT/LCD
- Ensures local monitoring even without cloud connectivity

---

## 🛠️ Development Environment
- Platform: **Arduino / ESP-IDF**
- Language: **C++**
- Libraries:
  - WiFi
  - PubSubClient (MQTT)
  - ArduinoJson
  - TWAI (CAN)

---

## 🔐 Security Note
- AWS certificates and private keys are **not included** in this repository for security reasons
- Users must configure their own AWS IoT credentials

---

## 📂 Project Contents
- `.ino` file – ESP32 application code
- JSON payload generation
- MQTT publish logic
- CAN receive and timeout detection logic

---

## ✅ Summary
The ESP32 firmware acts as a **bridge between the embedded CAN network and the cloud**, enabling real-time visualization, remote monitoring, and alert generation, forming the **gateway layer** of the IoT architecture.
