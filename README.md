# Arduino Light Controller

The **Arduino Light Controller** is a passive output board designed to provide simple, reliable **on/off control of up to 16 lighting channels** using an Arduino microcontroller. The board routes Arduino I/O pins directly to lighting outputs and includes optional onboard current‑limiting resistors for direct LED connection.

This controller is intended for use with the **Arduino CMRI Library** in conjunction with an associated CMRI‑compatible shield.

---

## Overview

The Arduino Light Controller connects Arduino digital or analog output pins to low‑current lighting loads. Each output is strictly **on or off**—there is no dimming, PWM, or active drive circuitry on the board.

The design emphasizes:

- Electrical simplicity  
- Clear signal routing  
- Safe use within Arduino current limits  
- Compatibility with Arduino CMRI‑based control systems  

---

## Key Characteristics

- 16 independent lighting output channels  
- On/off control only  
- Arduino 5 V I/O pins directly power outputs  
- Optional onboard 1 kΩ series resistors for LEDs  
- Jumper‑selectable resistor bypass per channel  
- Designed for Arduino CMRI Library usage with a compatible shield  
- Passive design (no relays, MOSFETs, or drivers)  

---

## Assembled Board

![Arduino Light Controller Assembled Board](./Arduino%20Light%20Controller.jpg)

The image above shows the assembled Arduino Light Controller PCB with all connectors and headers populated.

---

## Board Layout and Function

### Top of Board – Arduino Control Headers

At the **top edge of the board** is a row of **four 4‑pin headers**.

- These headers connect directly to **Arduino digital or analog output pins**
- Together they control **16 lighting channels**
- Each pin corresponds to **one lighting output**
- Typically connected via ribbon cable or directly from a CMRI‑compatible shield

Each Arduino output pin switches one lighting channel on or off.

---

### Middle of Board – Resistor Bypass Headers

In the **center of the board** are **two rows of eight 2‑pin headers**.

- Each header corresponds to **one lighting channel**
- These headers allow bypassing the onboard **1 kΩ series resistor**

#### Built‑In Current Limiting

- Each output includes a **1 kΩ resistor** in series
- This allows **LEDs to be connected directly** to the board without external resistors

#### Resistor Bypass

- If the connected lighting already includes its own resistance:
  - A jumper may be installed on the corresponding 2‑pin header
  - This **bypasses the onboard 1 kΩ resistor**

This provides flexibility for:
- Pre‑resisted LEDs  
- Commercial lighting assemblies  
- External resistor networks  

---

### Bottom of Board – Light Output Headers

At the **bottom edge of the board** is a row of **sixteen 2‑pin headers**.

- Each header corresponds directly to one Arduino control pin
- Used to connect the lighting loads

#### Output Polarity

- **Top pin:** Positive (Arduino output)  
- **Bottom pin:** Ground / Negative  

⚠️ **Important:**  
Lighting loads are powered **directly from Arduino I/O pins**.  
Do not exceed Arduino per‑pin or total I/O current limits.

---

### Power Bus and Daisy Chaining

As with other modules in this series, the board includes:

- One **3‑pin header in the top‑left corner**
- One **3‑pin header in the top‑right corner**

These headers provide a shared **power bus** for:

- **12 V**
- **5 V**
- **Ground**

#### Power Bus Notes

- Allows **daisy chaining multiple modules**
- Maximum combined current across the bus: **3 A**
- Intended for system power distribution only  
  (lighting outputs are not powered from this bus)

---

## Electrical Characteristics and Limitations

- Control type: **On/Off only**
- No dimming or PWM
- No active output drivers
- No isolation from Arduino I/O
- Outputs driven directly from Arduino pins
- Designed for low‑current lighting only

⚠️ **Exceeding Arduino current limits may damage the microcontroller.**

---

## Intended Use

This board is well suited for:

- Arduino CMRI‑based layouts
- Model railroad lighting and structures
- Control panels and indicators
- Building and interior lighting
- Any application requiring simple, predictable lighting control

---

## Limited Liability and Disclaimer

This project is provided as an **open‑source hardware design** and is offered **as‑is**, without warranty of any kind.

By using this design, documentation, or any assembled hardware provided by the author, you agree to the following:

- You assume **all responsibility** for proper electrical design, wiring, installation, and use
- The author makes **no guarantees** regarding suitability for any specific application
- The author shall not be held liable for:
  - Damage to equipment
  - Electrical failures
  - Personal injury
  - Property damage
  - Losses resulting from improper use, installation, or modification

Use of this project or any associated hardware constitutes acceptance of these terms.

---

## Availability and Purchase

Fully **assembled and tested** Arduino Light Controller boards are available.

- **Price:** $35 USD per board  
- **Shipping:** Additional, based on destination  
- **Contact:**  
  📧 scostella@seancostella.com  

Please contact the author for current availability, lead times, and shipping details.

---

## Reference Projects

This project integrates with the Arduino CMRI ecosystem. The following projects provide related hardware, firmware, and configuration support:

- **Arduino Mega CMRI WiFi**  
  Arduino sketch for Mega 2560 to operate as CMRI Node with an ESP8266-ESP01 providing WiFi connectivity.
  https://github.com/scostella/Arduino_Mega_CMRI_WiFi

- **ESP8266 WiFi Setup Utility**  
  ESP sketch to program the ESP8266-ESP01 to work with the Arduino Mega 2560 and connection configuration for your WiFi network.
  https://github.com/scostella/ESP8266WiFiSetup
  
- **KiCad Custom Library**  
  Library containing all project parts in all designs.
  https://github.com/scostella/KiCadLibrary

- **Arduino Mega CMRI WiFi Shield**  
  KiCad design for a shield for the Arduino Mega 2560 facilitating easy integration with the ESP8266-ESP01 and the CMRI modules listed below.
  https://github.com/scostella/Arduino_Mega_CMRI_WiFi_Shield

- **Arduino Accessory Controller**  
  KiCad design for a board to control accessories up to 1 amp.
  https://github.com/scostella/Arduino-Accessory-Controller

- **Arduino IR Sensor Module - 8 Port**  
  KiCad design for a board to use TCRT5000 IR module to sense object presence which can also be used in the Arduino Mega CMRI WiFi module to group sensors to create virtual block detection.
  https://github.com/scostella/Arduino_IR_Sensor_Module_-_8_Port

- **Arduino Tortoise Controller with Feedback - 8 Port**  
  KiCad design for a board to control Circuitron Tortoise Slow Motion Switch machines and provide feedback on switch position either controlled internally by the voltage applied to the tortoise or an external signal.
  https://github.com/scostella/Arduino_Tortoise_Controller_with_Feedback_-_8_Port

- **Arduino Light Controller**  
  KiCad design for a board to control low amperage lighting and other loads (<10ma) using the Arduino's 5V source.
  https://github.com/scostella/Arduino-Light-Controller

These projects may be used together to form a complete CMRI‑controlled lighting and I/O system.

---

## Repository Contents

```text
/
├── Arduino Light Controller.kicad_pcb        # KiCad PCB Layout
├── Arduino Light Controller.kicad_prl        # KiCad Project Settings
├── Arduino Light Controller.kicad_pro        # KiCad Project
├── Arduino Light Controller.kicad_sch        # KiCad Schematics
├── PowerLED.kicad_sch                        # KiCad Power and LED module
├── ResistorNet.kicad_sch                     # KiCad Light Control Resistor and Bypass module
├── Arduino Light Controller.jpg              # Board Rendering
└── README.md
