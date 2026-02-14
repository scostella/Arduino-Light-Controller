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

![Arduino Light Controller](Arduino%20Light%20Controller.jpg)

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

## Reference Projects

The Arduino Light Controller integrates with the Arduino CMRI ecosystem. The following projects provide related hardware, firmware, and configuration support:

- **Arduino Mega CMRI WiFi Shield**  
  https://github.com/scostella/Arduino_Mega_CMRI_WiFi_Shield

- **Arduino Mega CMRI WiFi**  
  https://github.com/scostella/Arduino_Mega_CMRI_WiFi

- **ESP8266 WiFi Setup Utility**  
  https://github.com/scostella/ESP8266WiFiSetup

These projects may be used together to form a complete CMRI‑controlled lighting and I/O system.

---

## Repository Contents