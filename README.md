# Home Automation with Telegram Bot and Temperature Control

This project combines a Telegram bot with a temperature sensor to control a boiler and a light remotely, as well as automatically regulate the boiler based on temperature readings.

## Hardware Requirements

- ESP8266 board (e.g., NodeMCU)
- DS18B20 temperature sensor
- Relay module to control the boiler and light
- Jumper wires

## Libraries Used

- FastBot library for Telegram bot interaction
- microDS18B20 library for temperature sensor communication

## Setup

1. Connect the components as follows:
  - DS18B20 data pin to D3 on ESP8266
  - Relay module to D6 (boiler) and D8 (light) on ESP8266
2. Install the required libraries in your Arduino IDE.
3. Replace the following placeholders in the code with your actual values:
  - `YOUR_WIFI_SSID`
  - `YOUR_WIFI_PASSWORD`
  - `YOUR_BOT_TOKEN` (obtained from BotFather on Telegram)
  - `YOUR_CHAT_ID` (your Telegram chat ID)

## Features

- **Telegram Bot Commands:**
  - `Kotel ON/OFF`: Manually turn the boiler on or off (manual mode only).
  - `Svet ON/OFF`: Manually turn the light on or off.
  - `auto`: Switch to automatic temperature control mode.
  - `manual`: Switch to manual control mode.
  - `Temp`: Get the current temperature and boiler status.
- **Automatic Temperature Control:**
  - If the temperature falls below `LOW_BOUND_TEMPERATURE` in automatic mode, the boiler turns on.
  - If the temperature rises above `HIGH_BOUND_TEMPERATURE` in automatic mode, the boiler turns off.

## Usage

1. Upload the code to your ESP8266 board.
2. Start a conversation with your Telegram bot.
3. Use the commands listed above to control the devices and check temperature.
