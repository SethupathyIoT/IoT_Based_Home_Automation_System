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
Password: xxxxxx

os installation and Alexa config
Install Home Assistant OS in VMware
Download Home Assistant OS (Virtual Machine Image)
1.	Go to the official Home Assistant website
2.	Virtual Machine (VM) > Download the VMDK image (for VMware)
3.	Extract the downloaded .xz file using 7-Zip or any extractor
________________________________________
Install & Set Up VMware
1.	Download VMware Workstation Player (if not installed)
2.	Install VMware and open it
________________________________________
Create a New Virtual Machine
1.	Open VMware Workstation Player
2.	Click Create a New Virtual Machine
3.	Select "I will install the OS later"
4.	Choose Linux > Other Linux 64-bit
5.	Set a VM name, e.g., HomeAssistant-VM
6.	Allocate 20GB+ disk space (Recommended: 32GB)
7.	Click Customize Hardware
o	Set Memory to 2GB+ (Recommended: 4GB)
o	Set Processors to 2 Cores+
o	Remove unnecessary hardware (USB, Sound)
________________________________________
Attach Home Assistant OS Disk
1.	Select "HomeAssistant-VM"
2.	Click Edit Virtual Machine Settings
3.	Click Add > Hard Disk > SATA > Use an existing virtual disk
4.	Select the Home Assistant VMDK file you extracted earlier
5.	Click Finish and Power On the Virtual Machine
________________________________________
First Boot & Access Home Assistant
1.	Wait for Home Assistant to boot (5-10 minutes)
2.	Open a web browser and enter:
arduino
http://homeassistant.local:8123
o	If this doesn’t work, check your VM’s IP address and use:
http://<YOUR_VM_IP>:8123
3.	Follow the Home Assistant setup wizard
________________________________________
Connect Home Assistant to Alexa
Home Assistant doesn’t work with Alexa directly; we need to use Home Assistant Cloud (Nabu Casa) or manual setup with Alexa Skills & MQTT.
Using Home Assistant Cloud 
1.	Open Home Assistant
2.	Go to Settings > Home Assistant Cloud
3.	Sign up for Nabu Casa and log in
4.	Enable Alexa Integration
5.	Open the Amazon Alexa App on your phone
6.	Go to Skills & Games and search for Home Assistant
7.	Click Enable Skill, then Link your Nabu Casa Account
8.	Alexa will now detect your Home Assistant devices

