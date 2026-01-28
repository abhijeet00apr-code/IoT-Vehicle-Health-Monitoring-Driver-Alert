# 🚗 IoT Based Vehicle Health Monitoring and Driver Alert System Using CAN and IoT

A comprehensive **real-time embedded and IoT-based system** designed to monitor vehicle health parameters and driver safety conditions using an **automotive-grade CAN communication network** and **cloud-based alerting**. The system enables real-time monitoring, fault detection, and proactive alerts for improved safety and reliability.

---

## 📋 Overview

This project designs and implements a **real-time Vehicle Health Monitoring and Driver Alert System** that continuously acquires data from multiple vehicle-related sensors, processes it locally using an embedded controller, and transmits it over the **CAN bus**.  

The processed data is:
- Displayed locally on a **TFT display**
- Remotely monitored using **cloud services**

An **event-based alert mechanism** is implemented to notify users through **email alerts** whenever predefined safety thresholds are exceeded.

---

## 🧩 System Block Diagram

<p align="center">
  <img src="Block_Diagram/block_diagram.jpeg" width="900"/>
</p>

This block diagram shows the **transmitter–receiver architecture** of the system, where sensor data is processed by STM32, transmitted over CAN, and sent to the cloud via ESP32.

---

## ⚙️ Key Functionalities

### 1️⃣ 🔥 Real-Time Engine Performance Monitoring
Continuous monitoring of critical engine parameters:
- Engine temperature  
- Engine oil level  
- Engine vibration  

The collected data is analyzed to evaluate engine health and detect abnormal operating conditions.

---

### 2️⃣ 👤 Driver Alert System
- Monitoring of driver hand presence on the steering wheel  
- Dual touch-sensor logic to detect unsafe hand removal  
- Alerts generated when unsafe driving behavior is detected  

---

### 3️⃣ 🔗 CAN-Based Communication
- Reliable and real-time data transfer using **CAN protocol**  
- Sensor data transmitted between ECUs with error detection  
- Automotive-grade communication ensures robustness and noise immunity  

---

### 4️⃣ 📺 Local Data Visualization
- Real-time system status and sensor values displayed on a **TFT display connected to ESP32**  
- Ensures local monitoring even without cloud connectivity  

---

### 5️⃣ ☁️ IoT Cloud Integration
- Sensor data published to **AWS IoT using MQTT**  
- Enables remote monitoring and system analysis  
- Supports scalability for fleet or multi-vehicle applications  

---

### 6️⃣ ⚠️ Real-Time Alerts & Notifications
- Predefined threshold-based alert mechanism  
- **AWS SNS** used to generate real-time **email alerts**  
- Alerts triggered during abnormal engine conditions or unsafe driving behavior  

---

## 🧰 Software Tools & Technologies

- Embedded C for STM32 firmware development  
- Arduino / ESP-IDF for ESP32 programming  
- CAN protocol using MCP2551 CAN controller  
- FreeRTOS for real-time task management  
- AWS IoT Core (MQTT) for cloud communication  
- AWS SNS for email alert notifications  

---

## 🛠️ System Implementation Steps

### Step 1️⃣: Hardware Setup
- Sensor interfacing and ECU integration  
- CAN bus configuration between nodes  
- ESP32 gateway setup for display and IoT  

---

### Step 2️⃣: Firmware Development
- Sensor data acquisition and processing  
- CAN message framing and transmission  
- ESP32 data reception and TFT display update  
- MQTT data publishing to AWS IoT  

---

### Step 3️⃣: Cloud Configuration
- AWS IoT device and policy configuration  
- MQTT topic creation  
- AWS IoT rules for threshold detection  
- SNS topic and email subscription setup  

---

### Step 4️⃣: Testing & Validation
- Sensor calibration and validation  
- CAN communication reliability testing  
- Threshold-based alert testing  
- End-to-end data flow verification  

---

## 🛠️ Hardware Setup

<p align="center">
  <img src="Images/hardware_setup.jpg" width="900"/>
</p>

The above image shows the complete hardware implementation of the system, including the STM32 controller, ESP32 gateway, sensors, CAN interface, and display modules mounted on a prototype board.

---

## 🚀 Benefits of the System

- Real-time vehicle health monitoring  
- Improved driver safety through alerts  
- Reliable CAN-based communication  
- Cloud-based remote monitoring  
- Reduced maintenance cost through early fault detection  
- Scalable architecture for real-world deployment  

---

## 📸 Working Demonstration

📌 Refer to the **Images** folder for real-time working photos, debugging screenshots, and cloud alert demonstrations.

---

## ✅ Conclusion

The proposed system successfully demonstrates a **real-time, CAN-based vehicle health monitoring and driver alert solution** with **IoT cloud integration**. Its scalable and reliable architecture makes it suitable for modern automotive and fleet monitoring applications.

---

## 🔮 Future Scope

- Integration of additional vehicle sensors (RPM, TPMS, battery health)  
- Predictive maintenance using data analytics  
- Mobile or web dashboard for monitoring  
- Enhanced security for CAN and IoT communication  
