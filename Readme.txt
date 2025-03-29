ESP32 IoT Smart Home Controller

Overview

This project is an ESPHome-based smart home automation system using an ESP32. It integrates temperature and humidity monitoring (DHT11 sensor) and home automation (relay control) with automatic temperature-based switching. The system seamlessly integrates with Home Assistant, allowing easy control via a web interface, automation rules, and voice commands through Alexa.

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

**Power Supply (5V)

Project Overview

1. Temperature and Humidity Monitoring

The DHT11 sensor is connected to GPIO4.

It sends temperature and humidity data to Home Assistant every 10 seconds.

The temperature is used to trigger automatic relay control.

2. Relay Control for Home Automation

Relays are connected to GPIO pins as follows:

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

Password: xxxxxx

Home Assistant OS Installation on VMware

1. Download Home Assistant OS (Virtual Machine Image)

Go to the official Home Assistant website

Select Virtual Machine (VM) > Download the VMDK image (for VMware)

Extract the downloaded .xz file using 7-Zip or any other extractor

2. Install & Set Up VMware

Download VMware Workstation Player (if not installed)

Install VMware and open it

3. Create a New Virtual Machine

Open VMware Workstation Player

Click Create a New Virtual Machine

Select "I will install the OS later"

Choose Linux > Other Linux 64-bit

Set a VM name, e.g., HomeAssistant-VM

Allocate 20GB+ disk space (Recommended: 32GB)

Click Customize Hardware

Set Memory to 2GB+ (Recommended: 4GB)

Set Processors to 2 Cores+

Remove unnecessary hardware (USB, Sound)

4. Attach Home Assistant OS Disk

Select "HomeAssistant-VM"

Click Edit Virtual Machine Settings

Click Add > Hard Disk > SATA > Use an existing virtual disk

Select the Home Assistant VMDK file you extracted earlier

Click Finish and Power On the Virtual Machine

5. First Boot & Access Home Assistant

Wait for Home Assistant to boot (5-10 minutes)

Open a web browser and enter:

http://homeassistant.local:8123

If this does not work, check your VM's IP address and use:

http://<YOUR_VM_IP>:8123

Follow the Home Assistant setup wizard

Connecting Home Assistant to Alexa

Home Assistant does not natively support Alexa. To integrate, use Home Assistant Cloud (Nabu Casa) or a manual setup with Alexa Skills & MQTT.

Using Home Assistant Cloud

Open Home Assistant

Go to Settings > Home Assistant Cloud

Sign up for Nabu Casa and log in

Enable Alexa Integration

Open the Amazon Alexa App on your phone

Go to Skills & Games and search for Home Assistant

Click Enable Skill, then Link your Nabu Casa Account

Alexa will now detect your Home Assistant devices
