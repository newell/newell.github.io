# Building a Nixie Tube Clock with ESP32-C3

I've recently completed a fun and challenging project: a fully functional nixie tube clock powered by an ESP32-C3 microcontroller. This clock combines retro aesthetics with modern technology, featuring six IN-12A Nixie tubes, a 3D-printed case, and various smart features, including WiFi provisioning, a web-based control interface, and motion sensing for sleep mode.

This blog post offers a brief overview of the project. For those looking to dive into the code and detailed build process, you can check out the full repository on GitHub. The clock is open-source and licensed under both the MIT and CERN Open Hardware licenses. You’ll find everything from CAD models to the ESP32 firmware there.

## Project Overview

### Features at a Glance
- **Nixie Tubes & Components**: Six IN-12A nixie tubes, four colon indicators, and a [high-voltage flyback converter](https://github.com/newell/hv-flyback-converter) for powering the tubes.
- **ESP32-C3 Microcontroller**: Handles all the heavy lifting, from NTP time syncing to managing a web server for clock settings.
- **Custom Case Design**: The case was designed using [build123d](https://github.com/gumyr/build123d), and you can view and download the CAD models from the repository.
- **Smart Features**: WiFi provisioning via Bluetooth, web-based control, motion sensing, LED color control, and more.

### Key Components
- **Microcontroller**: ESP32-C3 DevKitM-1
- **Power Supply**: High-voltage flyback converter
- **Interface**: Web-based control via WiFi (client and server)
- **Sensors**: Motion detection to enable sleep mode
- **Extras**: Hourly slot machine effect and LED cycling for added visual appeal

![Nixie Clock Image](https://github.com/user-attachments/assets/07f993d6-80e4-4be8-91cf-ca07ee2fea44)

## Design and Development

I started this project with a focus on combining the nostalgia of nixie tubes with modern features. From initial prototyping with a single tube and breadboard setup to final assembly with custom PCBs, the journey was both challenging and rewarding.

- **Case Design**: The clock's case was modeled using the Python-based CAD library build123d, allowing me to visualize the entire build in 3D before 3D-printing it.
- **Circuit Design**: I hand-soldered the first prototypes and the custom PCBs used in the final version.

![Case Design](https://github.com/user-attachments/assets/6d905a4e-8f06-46c9-aa65-b445b4101efb)

## Clock Control Interface

The clock features a web-based interface accessible via [esp-home.local](http://esp-home.local), where you can adjust settings in real-time. Whether it's changing time formats, controlling LEDs, or updating NTP servers, the interface is clean, responsive, and user-friendly.

### Interface Highlights:
- **WebSockets**: Real-time control of the clock settings
- **Customizable UI**: Set time, timezone, and visual preferences like LED colors directly from your browser

![Web Interface](https://github.com/user-attachments/assets/71b5c2da-ff7b-42fa-be0a-e68aa2519f6b)

## How to Get Involved

If you're interested in building a nixie tube clock of your own, all the resources are available in the [GitHub repository](https://github.com/newell/nixie-clock-esp32c3). The project is open-source and comes with detailed documentation on hardware design, firmware, and 3D models.


