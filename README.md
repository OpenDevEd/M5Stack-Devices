# **M5Stack Notes**

This repository documents a detailed exploration of the M5Stack hardware ecosystem, focusing on building small interactive devices that combine motion sensing, audio playback, LEDs, haptics, RFID, and ultra–low-power operation.

The research compares different families of M5Stack devices, evaluates their expandability, and maps out which modules, batteries, and accessories are compatible with each hardware form factor.

Device and accessory reference tables are included separately in this repository.



## 1. Overview

M5Stack provides a diverse range of ESP32-based development devices organised into several hardware families:

* **Core series (classic 5×5 cm)** — modular stackable controllers
* **CoreS3 series (new generation)** — advanced multimedia controllers
* **Stick series** — compact wearable-style devices
* **ATOM series** — ultra-small modular cubes
* **STAMP modules** — embedded boards for custom wiring

Each family has unique strengths and constraints, especially regarding audio, IMU functionality, battery integration, module compatibility, and power management.



## 2. Building Small Motion-Reactive Interactive Devices

To build compact interactive devices (e.g., “cubes”) that respond to shaking, rotation, or tapping, pair:

* a device with a **6-axis or 9-axis IMU**
* either a **built-in speaker** or an **I²S audio amplifier**
* optional **RGB LEDs** for visual effects
* a **small battery base** (e.g., Atomic Battery Base or TailBat)

Useful hardware options include:

* **ATOM Matrix** (25 NeoPixels, IMU)
* **StickC PLUS2** (IMU, vibration motor, small display)
* **ATOM Echo** (speaker onboard, needs external IMU)
* **CoreS3** (more advanced but larger)

These devices can play short sounds when moved, light up LEDs, vibrate, or react to orientation.



## 3. Ultra–Low-Power Behaviour and RTC-Based Wake-Up

To create devices that run for long periods and only wake occasionally, true **power gating** is required — not just ESP32 deep sleep.

The **M5Stamp Timer Power (BM8563)** enables:

* RTC alarms
* timed wake-ups
* fully powering the ESP32 board off (microamp consumption)
* timed reactivation

It requires manual wiring and is independent of M5Stack form factors, making it ideal for embedded low-power projects.



## 4. Adding Sound Capabilities

Many M5Stack boards lack onboard speakers. To play audio, consider:

* **StickC PLUS2 + Speaker Hat (MAX98357)**
* **ATOM Echo**
* **CoreS3** (built-in full I²S audio subsystem)
* **MAX98357 I²S amplifier modules** wired to ATOM or Stick devices
* **Audio Module (STM32G030)** for *classic Core* stackable devices

Short WAV/MP3 audio playback is feasible across the entire ecosystem when an appropriate amplifier is present.



## 5. RFID Interaction

RFID support is not built into any M5Stack Core or ATOM device. Use the **RFID Unit 2 (WS1850S)** over Grove (I²C/UART).

Compatible with:

* Core / Core2 / Fire
* CoreS3
* Stick series
* ATOM series

This enables actions such as sound or LED effects triggered by specific tags.



## 6. Device Family Comparison

### **CoreS3 Series**

Advanced multimedia devices with touchscreens, dual microphones, camera, IMU, and (on CoreS3) a magnetometer. Uses a new 30-pin base connector and does not support classic stack modules.

### **Classic Core Series (Core, Core2, Fire, AWS EduKit, M5GO kits)**

Designed around the 57×57 mm, 12-pin M-Bus form factor. Support stackable modules including:

* Battery modules
* Relay modules
* Audio Module (STM32G030)
* M5GO Bottom bases with 10 RGB LEDs

### **Stick Series**

Small rectangular devices with integrated battery, IMU, small LCD, and optional Hats (speaker, sensors, buttons). The PLUS2 model adds a vibration motor and improved PMIC.

### **ATOM Series**

Ultra-small cubes featuring minimal ESP32 boards, often with add-ons:

* **Matrix**: 25 NeoPixels + IMU
* **Echo**: speaker + microphone
* **Lite**: minimal I/O
* Use via Grove connectors or direct wiring.



## 7. Haptic Feedback

To add vibration feedback, consider devices with built-in motors:

* **Core2**
* **M5StickC PLUS2**

Other boards require wiring a coin-cell vibration motor.



## 8. Mounting and LEGO Integration

Physical construction can be supported using:

* **SandwichC Bricks** (LEGO-compatible mounting plates)
* **M3 screw kits**
* **M5 Box** for storage and prototyping

These allow embedding M5Stack hardware into toys, enclosures, and kinetic experiments.



## 9. LEDs and NeoPixel Effects

RGB LED capabilities vary by device:

* **ATOM Matrix** offers a 25-pixel NeoPixel matrix
* **Core Fire**, **M5GO**, **Core2 AWS EducKit** include 10-pixel LED bars in their M5GO bottoms
* **StickC PLUS2**, **ATOM Lite**, **ATOM Echo** each include a single RGB LED
* **CoreS3** has no onboard NeoPixels but works with M5GO Bottom3

These can be used for icons, animations, interaction cues, and visual feedback.



## 10. Understanding Module Stacking

Classic stack modules (battery, audio, relay, proto, etc.) only attach to:

* Core (Original)
* Core2
* Core Fire
* M5GO
* Core2 AWS EduKit

CoreS3 does not use the classic M-Bus; Stick and ATOM devices rely on Grove and wiring instead of stacking.

Selecting hardware requires understanding this difference, especially when combining power modules or expansion modules.



## 11. Educational and Toy Interaction Patterns

The research identifies several patterns for building interactive devices:

* shake-to-sound cubes
* direction-aware toys using magnetometers
* RFID-triggered responses
* sound/light objects embedded in LEGO structures
* wearable sound/noise devices
* low-power IoT nodes waking briefly to perform tasks
* touchscreen audio-visual gadgets using CoreS3

These patterns benefit from selecting the right combination of IMU, speaker, LEDs, and power hardware.



## 12. Magnetometer Availability

Only a few devices include a magnetometer:

* **CoreS3**
* **Core Fire**

Devices based on the MPU6886 (Stick series, ATOM Matrix, etc.) include only accelerometer + gyroscope.

Magnetometers enable compass features, orientation-corrected sensor fusion, and magnetic field detection.



## 13. Curated Hardware Set (as used in this project)

The following devices and modules form a versatile experimental toolkit:

* **CoreS3**
* **M5StickC PLUS2** + Speaker Hat
* **ATOM Matrix**
* **M5Stamp Timer Power** (RTC power gating)
* **RFID Unit 2**
* **Atomic Battery Base**
* **Mini Dual Button Unit**
* **SandwichC Bricks**
* **M3 Screw Kit**

This selection enables building portable sound toys, motion-reactive cubes, RFID-aware devices, and long-life low-power systems.



## 14. Reference Tables

Device and accessory reference tables have been placed below.

These tables include detailed information on:

* footprints
* battery types
* IMU and magnetometer
* audio capabilities
* LED systems
* vibration motors
* camera and microphones
* RTC presence
* module compatibility
* whether an item is in the current hardware basket



### 📦   DEVICE TABLE

|   Device             | Family       | 12-pin M-Bus | IMU | Mag | Display    | Speaker | Battery | SD | Vib | Camera | Mics   | RTC | Extra LEDs        | Where the pixels live        |
| -------------------- | ------------ | ------------ | --- | --- | ---------- | ------- | ------- | -- | --- | ------ | ------ | --- | ----------------- | ---------------------------- |
|   CoreS3             | Core (new)   | ✘            | ✔   | ✔   | 2.0" touch | ✔       | ✔       | ✔  | ✘   | ✔      | ✔ dual | ✔   | 0                 | None (unless adding Bottom3) |
| CoreS3 SE            | Core (new)   | ✘            | ✘   | ✘   | 2.0" touch | ✔       | ✘       | ✔  | ✘   | ✔      | ✔ dual | ✔   | 0                 | None                         |
| Core (Original)      | Core classic | ✔            | ✘   | ✘   | 2.0" LCD   | ✔       | ✘       | ✔  | ✘   | ✘      | ✘      | ✔   | 0                 | None                         |
| Core2                | Core classic | ✔            | ✔   | ✘   | 2.0" touch | ✔       | ✔       | ✔  | ✔   | ✘      | ✔      | ✔   | 0 (10 w/ Bottom2) | LEDs in Bottom2 only         |
| Core Fire            | Core classic | ✔            | ✔   | ✔   | 2.0" LCD   | ✔       | ✔       | ✔  | ✘   | ✘      | ✘      | ✔   |   10 SK6812       | In M5GO base                 |
| M5GO (Core kit)      | Core classic | ✔            | ✔   | ✘   | 2.0" IPS   | ✔       | ✔       | ✘  | ✘   | ✘      | ✔      | ✔   |   10 LEDs         | In M5GO base                 |
|   Core2 AWS EduKit   | Core classic | ✔            | ✔   | ✘   | 2.0" touch | ✔       | ✔       | ✔  | ✔   | ✘      | ✔      | ✔   |   10 LEDs         | In M5GO Bottom2              |
| M5StickC PLUS        | Stick        | ✘            | ✔   | ✘   | Small TFT  | Buzzer  | ✔       | ✘  | ✘   | ✘      | ✔      | ✔   | 0                 | None                         |
|   M5StickC PLUS2     | Stick        | ✘            | ✔   | ✘   | IPS TFT    | Buzzer  | ✔       | ✘  | ✔   | ✘      | ✔      | ✔   |   1 RGB           | On StickC PLUS2 main board   |
|   ATOM Matrix        | ATOM         | ✘            | ✔   | ✘   | 5×5 LEDs   | ✘       | ✘       | ✘  | ✘   | ✘      | ✘      | ✘   |   25 WS2812       | On front LED matrix          |
| ATOM Lite            | ATOM         | ✘            | ✘   | ✘   | None       | ✘       | ✘       | ✘  | ✘   | ✘      | ✘      | ✘   |   1 RGB           | On main board                |
| ATOM Echo            | ATOM         | ✘            | ✘   | ✘   | None       | ✔       | ✘       | ✘  | ✘   | ✘      | ✔      | ✘   |   1 RGB           | On main board                |



### 🔌   ACCESSORIES TABLE

| Accessory                               | What it does             | Footprint compatibility             | Where used                     |
| --------------------------------------- | ------------------------ | ----------------------------------- | ------------------------------ |
|   M5Stamp Timer Power                   | RTC + timed power gating | Universal (wired)                   | Ultra-low-power / wake control |
|   M5StickCPLUS Speaker Hat (MAX98357)   | Adds digital speaker     | Stick family                        | Audio output                   |
|   Atomic Battery Base                   | 200 mAh battery          | ATOM footprint                      | Portable ATOM builds           |
|   SandwichC Brick (x3)                  | Lego-compatible adapter  | Universal mechanical                | Mounting                       |
|   RFID Unit 2 (WS1850S)                 | RFID reader              | Any Grove-enabled device            | NFC-like reading               |
|   M5 Box                                | Storage                  | Universal                           | Storage                        |
|   M3 Screw Kit                          | Mounting hardware        | Universal                           | Assembly                       |
|   Mini Dual Button Unit                 | 2-button Grove input     | Universal                           | Input device                   |
| Audio Module (STM32G030)                | Stereo codec             | Classic Core stack                  | External audio                 |
| Core Battery Modules (13.2 etc.)        | Extra battery            | Classic 5×5                         | Stackable                      |
| M5GO bottom (RGB)                       | LED bar + battery        | Core2 / Core Fire / CoreS3 versions | Adds 10 LEDs                   |
| TailBat                                 | Battery                  | ATOM                                | Portable                       |
| Generic I²S amp                         | Speaker amp              | Any wired                           | External audio                 |

# Acknowledgement

Generated with help from LLMs (ChatGPT, Claude, Gemini).