🌦️ ESPHome Solar Weather Station (ESP32 + BME280 + Deep Sleep)

This project is a low-power, solar-powered weather station built with an ESP32 (NodeMCU-32S) and a BME280 sensor for measuring temperature, humidity, and air pressure.

It is designed for maximum energy efficiency using a dynamic deep sleep algorithm based on the measured solar voltage and is fully integrated into Home Assistant via ESPHome.

Perfect for outdoor and off-grid applications.

🔧 Features

✅ Temperature, humidity, and pressure measurement (BME280)
✅ Dew point and altitude calculation
✅ Solar and battery voltage monitoring
✅ Dynamic deep sleep based on solar input
✅ Battery level in % with status text
✅ Min/Max temperature and humidity tracking (daily reset)
✅ Deep sleep control via Home Assistant
✅ WiFi RSSI quality + system status
✅ Last update timestamp
✅ OTA updates
✅ Static IP + fallback hotspot
✅ Optimized for solar / battery usage

🧠 Dynamic Deep Sleep Logic

Sleep duration is automatically adjusted based on solar voltage:

Solar Voltage	Sleep Time
> 4.5 V	20 minutes
> 2.5 V	35 minutes
> 1.0 V	45 minutes
≤ 1.0 V	70 minutes


Deep sleep can also be manually enabled/disabled using the Home Assistant entity:

input_boolean.wetterstation_deep_sleep


🔋 Power System

Battery voltage reading via ADC + voltage divider (R1 / R2)

Percentage calculation based on 3.2 V – 4.2 V

Text status: Full / OK / Low / Critical

Solar voltage is used to control sleep cycle duration

📦 Hardware

ESP32 NodeMCU-32S

BME280 (I2C address: 0x76)

Li-Ion battery

Solar panel

Voltage divider (R1 = 97kΩ, R2 = 26.8kΩ – adjustable)

Outdoor enclosure (recommended)

🏠 Home Assistant Integration

The station exposes the following main entities:

Temperature, humidity, pressure

Dew point & altitude

Min/Max (temperature and humidity)

Battery percentage

Solar voltage

Wake-ups per day

Last update

Sleep mode state

WiFi signal quality

Connected via ESPHome API (encrypted).

🗂 Configuration Overview

Platform: ESP32 (nodemcu-32s)

Framework: Arduino

BME280 via I²C (SDA 21 / SCL 22)

ADC:

GPIO34 → Battery

GPIO35 → Solar

Dynamic deep sleep control via scripts

🚀 Planned Extensions
