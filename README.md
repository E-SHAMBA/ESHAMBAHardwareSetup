# ESHAMBAHardwareSetup
# Smart Irrigation System

## Overview

This code is designed for an ESP32-based Smart Irrigation System that monitors environmental conditions and controls irrigation based on predefined schedules. The system utilizes various sensors, including the AHT10 sensor for temperature and humidity, a light sensor, and a soil moisture sensor. Additionally, it integrates a real-time clock (RTC) module for accurate timekeeping.

## Features

- **Temperature and Humidity Monitoring:** The AHT10 sensor provides real-time temperature and humidity data, allowing precise environmental monitoring.

- **Light Intensity Sensing:** A light sensor is employed to measure light intensity, enabling the system to adapt to varying lighting conditions.

- **Soil Moisture Detection:** The soil moisture sensor gauges the moisture content of the soil, ensuring optimal irrigation based on soil conditions.

- **MQTT Communication:** The system communicates with an MQTT broker to send sensor data and receive commands, allowing remote control and monitoring.

- **Scheduled Irrigation:** The system includes a real-time clock (RTC) module for scheduling irrigation at specific times. The irrigation can be activated remotely through MQTT commands.

## Components Used

- ESP32 microcontroller
- AHT10 temperature and humidity sensor
- RTC DS3231 module
- Light sensor
- Soil moisture sensor
- MQTT communication via PubSubClient library

## Setup Instructions

1. **Connect Sensors:** Wire the AHT10, RTC DS3231, light sensor, and soil moisture sensor to the specified GPIO pins on the ESP32.

2. **Configure Wi-Fi:** Set your Wi-Fi credentials by filling in the `WIFI_SSID` and `WIFI_PASS` variables in the code.

3. **MQTT Configuration:** Provide the MQTT broker details by setting the `mqtt_server` variable.

4. **Adjust Thresholds:** Modify the `dryValue` and `wetValue` variables according to the soil moisture levels that define when the soil is dry or wet.

5. **Compile and Upload:** Use the Arduino IDE or your preferred development environment to compile and upload the code to your ESP32.

6. **Monitor and Control:** Access the MQTT broker to monitor sensor data and send commands for pump control, fan control, and scheduling irrigation.

## MQTT Topics

- `pump`: Command topic for pump control (`ON` to turn on, `OFF` to turn off).
- `fan`: Command topic for fan control.
- `time`: Command topic for adjusting the system time.
- `onHour`: Topic for setting the irrigation hour.
- `onMin`: Topic for setting the irrigation minute.

## Dependencies

- WiFi library
- PubSubClient library
- AHT10 library
- Wire library
- RTClib library

## Notes

- Ensure that the required libraries are installed in your Arduino IDE before uploading the code.

- For scheduled irrigation, set the desired irrigation time by publishing values to the `onHour` and `onMin` topics.

- The MQTT broker must be running and reachable for proper communication.

Feel free to adapt and extend this code to suit your specific requirements. Happy coding!

