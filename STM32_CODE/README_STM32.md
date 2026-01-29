# STM32 Firmware – Vehicle Health Monitoring ECU

## 📌 Overview
This folder contains the firmware for the **STM32F407VGT6** microcontroller, which acts as the **sensor acquisition and CAN transmitter node** in the IoT-based Vehicle Health Monitoring and Driver Alert System.

The STM32 controller collects real-time vehicle and driver-related data, processes it locally using **FreeRTOS**, and transmits the data over the **CAN bus** to the ESP32 gateway.

---

## 🎯 Responsibilities of STM32
- Real-time acquisition of vehicle parameters
- Local processing and filtering of sensor data
- Driver alert logic execution
- CAN data frame formation and transmission

---

## 🔧 Sensors Interfaced
- Engine temperature sensor  
- Engine oil level sensor (ultrasonic-based)  
- Accelerometer for engine vibration monitoring  
- Dual touch sensors for driver hand detection  

---

## ⚙️ Software Architecture
- **RTOS**: FreeRTOS  
- **Task 1 – Sensor Task**
  - Reads all sensors periodically
  - Processes raw sensor values
  - Updates driver alert logic
- **Task 2 – CAN Task**
  - Packages sensor data into CAN data frames
  - Transmits data to ESP32 over CAN
- **Synchronization**
  - Binary semaphore used to protect shared data

---

## 🔗 CAN Communication
- CAN Mode: Standard CAN (11-bit Identifier)
- CAN ID: `0x123`
- Baud Rate: `500 kbps`
- Data Length: 8 bytes
- Payload includes:
  - Temperature
  - Oil level
  - Vibration data
  - Driver touch status

---

## 🛠️ Development Environment
- IDE: **STM32CubeIDE**
- Language: **Embedded C**
- HAL Drivers
- CMSIS
- FreeRTOS Middleware

---

## 📂 Project Contents
- `Core/Inc` – Header files  
- `Core/Src` – Source files  
- `Drivers/` – STM32 HAL & CMSIS  
- `Middlewares/` – FreeRTOS  
- `.ioc` – STM32CubeMX configuration file  

---

## ⚠️ Notes
- Build folders (`Debug/`, `Release/`) are intentionally excluded
- Only source and configuration files are uploaded for portability

---

## ✅ Summary
The STM32 firmware ensures **deterministic real-time behavior**, reliable CAN communication, and robust sensor data acquisition, forming the **perception layer** of the overall IoT system.
