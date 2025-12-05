
# 📦 **DEVICE TABLE

| **Device**           | Family       | 12-pin M-Bus | IMU | Mag | Display    | Speaker | Battery | SD | Vib | Camera | Mics   | RTC | Extra LEDs        | Where the pixels live        |
| -------------------- | ------------ | ------------ | --- | --- | ---------- | ------- | ------- | -- | --- | ------ | ------ | --- | ----------------- | ---------------------------- |
| **CoreS3**           | Core (new)   | ✘            | ✔   | ✔   | 2.0" touch | ✔       | ✔       | ✔  | ✘   | ✔      | ✔ dual | ✔   | 0                 | None (unless adding Bottom3) |
| CoreS3 SE            | Core (new)   | ✘            | ✘   | ✘   | 2.0" touch | ✔       | ✘       | ✔  | ✘   | ✔      | ✔ dual | ✔   | 0                 | None                         |
| Core (Original)      | Core classic | ✔            | ✘   | ✘   | 2.0" LCD   | ✔       | ✘       | ✔  | ✘   | ✘      | ✘      | ✔   | 0                 | None                         |
| Core2                | Core classic | ✔            | ✔   | ✘   | 2.0" touch | ✔       | ✔       | ✔  | ✔   | ✘      | ✔      | ✔   | 0 (10 w/ Bottom2) | LEDs in Bottom2 only         |
| Core Fire            | Core classic | ✔            | ✔   | ✔   | 2.0" LCD   | ✔       | ✔       | ✔  | ✘   | ✘      | ✘      | ✔   | **10 SK6812**     | In M5GO base                 |
| M5GO (Core kit)      | Core classic | ✔            | ✔   | ✘   | 2.0" IPS   | ✔       | ✔       | ✘  | ✘   | ✘      | ✔      | ✔   | **10 LEDs**       | In M5GO base                 |
| **Core2 AWS EduKit** | Core classic | ✔            | ✔   | ✘   | 2.0" touch | ✔       | ✔       | ✔  | ✔   | ✘      | ✔      | ✔   | **10 LEDs**       | In M5GO Bottom2              |
| M5StickC PLUS        | Stick        | ✘            | ✔   | ✘   | Small TFT  | Buzzer  | ✔       | ✘  | ✘   | ✘      | ✔      | ✔   | 0                 | None                         |
| **M5StickC PLUS2**   | Stick        | ✘            | ✔   | ✘   | IPS TFT    | Buzzer  | ✔       | ✘  | ✔   | ✘      | ✔      | ✔   | **1 RGB**         | On StickC PLUS2 main board   |
| **ATOM Matrix**      | ATOM         | ✘            | ✔   | ✘   | 5×5 LEDs   | ✘       | ✘       | ✘  | ✘   | ✘      | ✘      | ✘   | **25 WS2812**     | On front LED matrix          |
| ATOM Lite            | ATOM         | ✘            | ✘   | ✘   | None       | ✘       | ✘       | ✘  | ✘   | ✘      | ✘      | ✘   | **1 RGB**         | On main board                |
| ATOM Echo            | ATOM         | ✘            | ✘   | ✘   | None       | ✔       | ✘       | ✘  | ✘   | ✘      | ✔      | ✘   | **1 RGB**         | On main board                |

---

# 🔌 **ACCESSORIES TABLE

| Accessory                               | What it does             | Footprint compatibility             | Where used                     |
| --------------------------------------- | ------------------------ | ----------------------------------- | ------------------------------ |
| **M5Stamp Timer Power**                 | RTC + timed power gating | Universal (wired)                   | Ultra-low-power / wake control |
| **M5StickCPLUS Speaker Hat (MAX98357)** | Adds digital speaker     | Stick family                        | Audio output                   |
| **Atomic Battery Base**                 | 200 mAh battery          | ATOM footprint                      | Portable ATOM builds           |
| **SandwichC Brick (x3)**                | Lego-compatible adapter  | Universal mechanical                | Mounting                       |
| **RFID Unit 2 (WS1850S)**               | RFID reader              | Any Grove-enabled device            | NFC-like reading               |
| **M5 Box**                              | Storage                  | Universal                           | Storage                        |
| **M3 Screw Kit**                        | Mounting hardware        | Universal                           | Assembly                       |
| **Mini Dual Button Unit**               | 2-button Grove input     | Universal                           | Input device                   |
| Audio Module (STM32G030)                | Stereo codec             | Classic Core stack                  | External audio                 |
| Core Battery Modules (13.2 etc.)        | Extra battery            | Classic 5×5                         | Stackable                      |
| M5GO bottom (RGB)                       | LED bar + battery        | Core2 / Core Fire / CoreS3 versions | Adds 10 LEDs                   |
| TailBat                                 | Battery                  | ATOM                                | Portable                       |
| Generic I²S amp                         | Speaker amp              | Any wired                           | External audio                 |

