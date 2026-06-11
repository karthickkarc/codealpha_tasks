# IoT Task 2 – Sensor-Based Simulation (LDR + LED Control)

> **CodeAlpha Internship** – Internet of Things (IoT) | Task 2

---

## 📌 Overview

This project demonstrates how an **LDR (Light Dependent Resistor)** sensor can be used to detect ambient light intensity and dynamically control the blinking speed of 3 LEDs using an **Arduino UNO**.

- Brighter environment → **faster** LED blinking  
- Darker environment → **slower** LED blinking

---

## 🔁 Program Flow

```
Start
 ↓
Initialize LEDs and Serial Monitor
 ↓
Read LDR Value
 ↓
Convert to Light Percentage
 ↓
Calculate Delay Time
 ↓
Display Data on Serial Monitor
 ↓
Blink LED1 → Blink LED2 → Blink LED3
 ↓
Repeat Forever
```

---

## 🛠️ Components Used

| Component        | Quantity |
|------------------|----------|
| Arduino UNO      | 1        |
| LDR (Photoresistor) | 1     |
| LED              | 3        |
| Resistors        | 3        |
| Breadboard       | 1        |
| Jumper Wires     | As needed |

---

## 📌 Pin Configuration

| Component | Arduino Pin |
|-----------|-------------|
| LDR       | A0          |
| LED 1     | D8          |
| LED 2     | D9          |
| LED 3     | D10         |

---

## 🎛️ Calibration Values

| Light Condition | LDR Raw Value |
|-----------------|---------------|
| Dark            | 54            |
| Bright          | 974           |

---

## ⏱️ Delay Mapping

| Light Intensity | Blink Delay |
|-----------------|-------------|
| 0% (Dark)       | 1000 ms     |
| 50% (Medium)    | 550 ms      |
| 100% (Bright)   | 100 ms      |

> **More light → smaller delay → faster blinking**  
> **Less light → larger delay → slower blinking**

---

## 💻 Code Logic

### 1. Reading the LDR
```cpp
int ldrValue = analogRead(ldrPin); // Returns 0–1023
```

### 2. Converting to Light Percentage
```cpp
int lightPercent = map(ldrValue, minLDR, maxLDR, 0, 100);
lightPercent = constrain(lightPercent, 0, 100);
```

### 3. Calculating Blink Delay
```cpp
int delayTime = map(lightPercent, 0, 100, 1000, 100);
```

### 4. Serial Monitor Output Example
```
Raw LDR: 650 | Light Intensity: 65 % | Delay: 415 ms
```

---

## 🔗 Tinkercad Simulation

[▶ View Live Simulation on Tinkercad](https://www.tinkercad.com/things/fJwOzT8uSDM-codealphakarthicksiot?sharecode=EMJvqWanquYgYwzlU5EkOresA-STmaJPyrmJwah_YvY)

---

## 📁 Repository Structure

```
CodeAlpha_IoT_Task2/
├── README.md
├── ldr_led_control.ino
└── assets/
    └── circuit_diagram.png
```

---

## 👤 Author

**Karthick S**  
CodeAlpha Internship – IoT Domain
