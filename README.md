# land-safe-explorer
GPS-guided autonomous robot for landmine detection using GPR &amp; metal-sensor fusion
---

## 🔧 Hardware Components

| # | Component | Model | Qty | Purpose |
|---|-----------|-------|-----|---------|
| 1 | Microcontroller | Arduino Mega 2560 | 1 | Main controller |
| 2 | GPS Module | NEO-6M (GY-NEO6MV2) | 1 | Positioning & waypoints |
| 3 | Motor Driver | L298N Dual H-Bridge | 1 | Motor speed & direction |
| 4 | Metal Detector | Inductive Sensor Module | 1 | Mine detection |
| 5 | Robot Chassis | 4WD Smart Car Kit | 1 | Base platform |
| 6 | SD Card Module | SPI Interface | 1 | GPS data logging |
| 7 | DC Gear Motors | TT Motor 3–6V | 4 | Locomotion |
| 8 | Li-Po Battery | 7.4V 2200mAh | 1 | Power supply |
| 9 | Buck Converter | LM2596 | 1 | 7.4V → 5V regulation |
| 10 | Active Buzzer | 5V Buzzer | 1 | Detection alert |
| 11 | LED (Red) | 5mm LED | 1 | Visual alert |
| 12 | Jumper Wires | M-M / M-F / F-F | — | Connections |

---

## 🔌 Pin Connections

### GPS Module (NEO-6M) → Arduino Mega
| NEO-6M Pin | Arduino Mega Pin |
|------------|-----------------|
| VCC | 5V |
| GND | GND |
| TX | RX1 (Pin 19) |
| RX | TX1 (Pin 18) |

### L298N Motor Driver → Arduino Mega
| L298N Pin | Arduino Mega Pin |
|-----------|-----------------|
| IN1 | Pin 2 |
| IN2 | Pin 3 |
| IN3 | Pin 4 |
| IN4 | Pin 5 |
| ENA | Pin 9 (PWM) |
| ENB | Pin 10 (PWM) |
| GND | GND |

### SD Card Module → Arduino Mega
| SD Pin | Arduino Mega Pin |
|--------|-----------------|
| CS | Pin 53 |
| MOSI | Pin 51 |
| MISO | Pin 50 |
| SCK | Pin 52 |
| VCC | 5V |
| GND | GND |

### Metal Detector → Arduino Mega
| Sensor Pin | Arduino Mega Pin |
|------------|-----------------|
| VCC | 5V |
| GND | GND |
| OUT | Pin 7 (Digital) |

### Buzzer & LED → Arduino Mega
| Component | Arduino Pin |
|-----------|------------|
| Buzzer (+) | Pin 11 |
| LED (+) | Pin 12 |
| Both (–) | GND |

---

## ⚙️ Installation & Setup

### 1. Clone the Repository
```bash gitclone https://github.com/YOUR_USERNAME/land-safe-explorer.git
cd land-safe-explorer
```

### 2. Install Required Libraries
Open Arduino IDE → Sketch → Include Library → Manage Libraries

Search and install:
### 3. Set Your GPS Waypoints
Open `firmware/main/main.ino` and edit:
```cpp
// Add your target waypoints here
float waypoints[][2] = {
  {17.3850, 78.4867},   // Waypoint 1
  {17.3855, 78.4872},   // Waypoint 2
  {17.3860, 78.4880},   // Waypoint 3
};
```

### 4. Upload to Arduino
