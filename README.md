# Arduino-Based Hexacopter Drone Flight Controller

Welcome to the repository for my school project: an **Arduino-based Hexacopter Drone**. 

This project features custom flight controller firmware capable of stabilizing and piloting a 6-motor (hexacopter) configuration. The software is built upon the well-known open-source **YMFC-AL (Auto-Leveling)** quadcopter code by Joop Brokking, heavily modified to accommodate the physics, mixing, and hardware requirements of a hexacopter.

---

## 🚀 Features
* **Auto-Leveling (AL):** Employs an IMU (Gyro/Accelerometer) to automatically stabilize the drone when the transmitter sticks are centered.
* **Hexacopter Mixing:** Modified motor mixing algorithms to distribute roll, pitch, yaw, and throttle commands across 6 brushless motors (instead of the original 4).
* **Arduino Architecture:** Built using the Arduino platform for accessible hardware integration and real-time I/O processing.

---

## 🛠️ Hardware Stack
* **Microcontroller:** Arduino Uno / Nano (or state your specific board, e.g., Arduino Mega)
* **IMU Sensor:** MPU-6050 (Gyroscope + Accelerometer)
* **Frame:** Hexacopter Frame (e.g., F550)
* **Motors:** 6x Brushless DC Motors + 6x ESCs (Electronic Speed Controllers)
* **Receiver:** 4+ Channel RC Receiver (Flysky FS-IA6B)
* **Transmitter:** 4+ Channel RC Transitter (Flysky FS-i6x)

---

## 💻 Software Modifications & Acknowledgments
The backbone of this firmware is the brilliant **YMFC-AL** project by Joop Brokking ([Brokking.ch / YouTube](https://www.youtube.com/user/Brokking)). 

### What I Changed:
1. **Motor Mixing Algorithm:** Rewrote the pulse calculation logic to calculate signals for 6 ESCs rather than 4, ensuring correct counter-rotating pairs for hexacopter stabilization.
2. **Hardware Interrupts/Pins:** Expanded the Arduino output pin routine to send timed pulses to two additional ESC outputs simultaneously.
3. **PID Tuning:** Adjusted the proportional, integral, and derivative loops to handle the extra thrust and inertia of a 6-rotor chassis.

---

## 📂 Project Structure
* `/Firmware` - The modified Arduino sketches (`.ino` files).
* `/Documentation` - School project reports, wiring diagrams, and schematics.

---

## ⚠️ Disclaimer
This project was developed as a school assignment for educational purposes. Operating DIY drones with custom firmware carries inherent risks. Always remove propellers when testing the drone on the bench!
