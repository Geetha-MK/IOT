# 🔥 Fire Alarm System using ESP8266

## 📌 Overview
The **Fire Alarm System** is an IoT-based embedded project designed to detect fire hazards using a flame sensor and alert users through a buzzer. The system uses ESP8266 (NodeMCU) for real-time monitoring and quick response to fire incidents.

---

## 🎯 Objective
- Detect fire using flame sensor
- Provide immediate alert using buzzer
- Ensure safety in homes, labs, and workplaces
- Enable basic IoT-based monitoring

---

## 🧩 Block Diagram

---

## 🔄 Flowchart
- START
↓
Initialize System
↓
Read Flame Sensor
↓
Fire Detected?
↓ ↓
YES NO
↓ ↓
Activate Continue Monitoring
Buzzer
↓
Alert User

---

## ⚙️ Working Principle
- Flame sensor continuously detects fire or infrared radiation
- ESP8266 reads sensor output
- If fire is detected:
  - Buzzer is activated
  - Alert is generated
- If no fire:
  - System continues monitoring

---

## 🧩 Components Used
- ESP8266 (NodeMCU)  
- Flame Sensor  
- Buzzer  
- Jumper Wires  
- Breadboard  
- Power Supply  

---

## 🔌 Circuit Connections
- Flame Sensor → Digital Pin (D1)  
- Buzzer → Digital Pin (D2)  
- VCC → 3.3V  
- GND → GND  

---

## 💻 Arduino Code

```cpp
const int flamePin = D1;
const int buzzerPin = D2;

void setup() {
  pinMode(flamePin, INPUT);
  pinMode(buzzerPin, OUTPUT);
  Serial.begin(9600);
}

void loop() {
  int flameStatus = digitalRead(flamePin);

  if (flameStatus == LOW) {  // Fire detected
    digitalWrite(buzzerPin, HIGH);
    Serial.println("🔥 Fire Detected!");
  } 
  else {
    digitalWrite(buzzerPin, LOW);
    Serial.println("No Fire");
  }

  delay(500);
}
↓
END
