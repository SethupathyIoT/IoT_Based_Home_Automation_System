ESP32 IoT Smart Home Controller
This project is an ESPHome-based smart home automation system using an ESP32. It integrates temperature and humidity monitoring (DHT11 sensor) and home automation (relay control) with automatic temperature-based switching.

Features
DHT11 Sensor: Monitors room temperature and humidity.

Relay Control: Supports four relays to control home appliances.

Auto-Control: Relay 4 automatically turns ON/OFF based on temperature.

Home Assistant Integration: Works seamlessly with Home Assistant.

Fallback Access Point: If WiFi is unavailable, the device creates a fallback hotspot.

Over-the-Air (OTA) Updates: Firmware can be updated wirelessly.

Hardware Requirements
ESP32

DHT11 Temperature & Humidity Sensor

4-Channel Relay Module

WiFi Network

Power Supply (5V)

Project Overview
1. Temperature and Humidity Monitoring
The DHT11 sensor is connected to GPIO4.

It sends temperature and humidity data to Home Assistant every 10 seconds.

The temperature is used to trigger automatic relay control.

2. Relay Control for Home Automation
Relays are connected to GPIO pins:

Relay 1 → GPIO18

Relay 2 → GPIO19

Relay 3 → GPIO21

Relay 4 → GPIO22

They can be controlled via Home Assistant or automatically based on temperature.

3. Auto-Control for Relay 4
If the room temperature exceeds 30°C, Relay 4 turns ON.

If the temperature drops below 30°C, Relay 4 turns OFF.

4. WiFi & Fallback Access Point
Connects to the configured WiFi SSID.

If WiFi is unavailable, it creates a fallback hotspot:
SSID: Controller Fallback Hotspot
Password: SILK@IOT