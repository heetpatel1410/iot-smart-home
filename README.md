# 🏠 IoT Smart Home Project

This project allows you to **monitor and control home appliances** using **IoT (Internet of Things)**.  
It is built using **ESP32**, **DHT11 sensor**, **smoke sensor**, and **relay module** — all connected to the **Blynk Cloud platform**.

---

## 🔌 Features
- 🌡️ Monitor temperature and humidity using DHT11  
- 💨 Detect smoke/gas with MQ-2 sensor  
- 💧 Track soil moisture for irrigation system (Can be added for smart irrigation for plants on your home)
- 💡 Control fan or light remotely through Blynk app  
- 📶 Real-time data monitoring over Wi-Fi

---

## ⚙️ Hardware Used
| Component              | Description |
|------------------------|-------------|
| ESP32                  | Main controller board with Wi-Fi |
| DHT11                  | Temperature and humidity sensor |
| MQ-2                   | Smoke sensor |
| Soil Moisture Sensor   | Detects moisture in soil |
| 1-Channel Relay Module | Controls fan or light |

---

## 🧠 Working
- The ESP32 reads data from all sensors.
- Sends live readings to **Blynk Cloud** via Wi-Fi.
- The user can control devices (like a fan or bulb) using the **Blynk mobile app**.
- Example:
  - When temperature > 30°C → Fan turns ON automatically.
  - When soil is dry → Irrigation relay activates.
--

## 🧰 Software Used
- Arduino IDE  
- Blynk Cloud (for IoT dashboard)  
- Wi-Fi connection for ESP32  

---

## 🚀 How to Run
1. Open the `.ino` file in Arduino IDE.  
2. Enter your **Wi-Fi credentials** and **Blynk auth token**.  
3. Upload the code to ESP32.  
4. Open Blynk app → Create dashboard → Add switches and gauges.  
5. Watch real-time data and control devices!

---
## 📚 References / Acknowledgements
This project was developed with help from online resources and tutorials for learning purposes.  
Special thanks to SST Technologies (for providing development boards and guidance)
 -- Link : https://github.com/sst-tech

## ✨ Author
**Heet Patel**  
GitHub: [@heetpatel1410](https://github.com/heetpatel1410)

---

