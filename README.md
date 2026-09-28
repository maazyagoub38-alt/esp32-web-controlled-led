# ESP32 Web-Controlled LED

A beginner-friendly embedded/IoT project that controls an LED connected to an ESP32 through a web browser over a local Wi-Fi network.

## Project Overview

The ESP32 connects to a Wi-Fi network and runs a simple HTTP web server. A user can open the ESP32 local IP address in a browser and use ON/OFF buttons to control the LED connected to GPIO 23.

## System Architecture

```text
Phone / Laptop
      |
      | Wi-Fi
      v
Web Browser
      |
      | HTTP
      v
ESP32 Web Server
      |
      v
GPIO 23
      |
      v
LED + 220 ohm
      |
      v
     GND
```

## Hardware

- ESP32 development board
- LED
- 220 ohm resistor
- Breadboard
- Jumper wires
- USB cable

## Wiring

| Component | ESP32 |
|---|---|
| LED anode (+) through 220 ohm resistor | GPIO 23 |
| LED cathode (-) | GND |

## Software

- Arduino IDE
- C++
- ESP32 Arduino Core
- Wi-Fi
- HTTP

## How It Works

1. The ESP32 connects to the configured Wi-Fi network.
2. It starts an HTTP web server on port 80.
3. The root page displays ON/OFF controls.
4. `/on` sets GPIO 23 HIGH.
5. `/off` sets GPIO 23 LOW.
6. The browser is redirected back to the control page.

## Setup

1. Install ESP32 board support in Arduino IDE.
2. Open `src/esp32_web_led.ino`.
3. Replace the Wi-Fi placeholders with your local credentials.
4. Select the correct ESP32 board and USB port.
5. Upload the program.
6. Open Serial Monitor at **115200 baud**.
7. Read the IP address printed by the ESP32.
8. Open that IP address in a browser connected to the same Wi-Fi network.

Example:

```text
http://192.168.1.105
```

## Security Note

Do not commit real Wi-Fi credentials to a public GitHub repository. For a public repository, store credentials in a local `secrets.h` file and add that file to `.gitignore`.

## Project Structure

```text
esp32-web-controlled-led/
├── README.md
├── .gitignore
├── src/
│   └── esp32_web_led.ino
├── hardware/
│   └── wiring.md
└── docs/
    └── project-notes.md
```

## What I Learned

- ESP32 Wi-Fi connectivity
- GPIO and digital output
- Basic HTTP requests
- Running a web server on a microcontroller
- Connecting a web interface to physical hardware
- Basic Git/GitHub project documentation

## Future Improvements

- Improve the web interface for mobile devices
- Add LED status feedback
- Control multiple LEDs
- Control an RGB LED
- Add authentication
- Add sensors
- Explore MQTT-based IoT control
- Connect the system to a secure remote backend

## Author

**Maaz Yagoub**
