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
