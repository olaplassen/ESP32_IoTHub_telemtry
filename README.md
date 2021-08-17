# ESP32_IoTHub_telemtry
Based on the "esp32/iothub_ll_telemetry_sample" from [Azure IoT Arduino](https://github.com/Azure/azure-iot-arduino)
This library is a port of the Microsoft Azure IoT device SDK for C to Arduino. It is an Arduino script for ESP32 to generate IoTHub messages with telemetry data from a connected BME280 sensor. The script is intended to send data to IoThHub with the correct systemproperties which in turn fires an event and updates the corresponding Azure Digital Twins value. 

Information flow: 

ESP32 + BME280 -> Azure IoTHub -> Azure Event Grid -> Azure Function -> Azure Digital twins.

## Prerequisites
You should have the following resources ready before beginning with your board:

Setup your IoT hub

Provision your device and get its credentials

Install [Arduino IDE](https://www.arduino.cc/en/software)
- Start Arduino and open Preferences window.
- Enter https://dl.espressif.com/dl/package_esp32_index.json into Additional Board Manager URLs field. You can add multiple URLs, separating them with commas.
- Open Boards Manager from Tools > Board menu and install esp32 platform 1.0.2 or later
- Select your ESP32 board from Tools > Board menu after installation

- Install the following libraries through the Arduino IDE Library Manager: AzureIoTHub, AzureIoTUtility, AzureIoTProtocol_MQTT, AzureIoTProtocol_HTTP

Wire the BME280 sensor to your ESP32 chip.
- **ESP** - **BME280**
- P22 - SCK
- P21 - SDI
- 3V3 - VIN
- GND - GND

## Run the sample
Clone the repository and open the final_esp32_script.ino file in Arduino Ide. 
Enter the following information in:
[config.h](https://github.com/olaplassen/ESP32_IoTHub_telemtry/blob/main/iot_configs.h)
- IOT_CONFIG_WIFI_SSID(wifi name)
- IOT_CONFIG_WIFI_PASSWORD(wifi password)
- DEVICE_CONNECTION_STRING(primary connection string from iothub device) <br />
NB! **The wifi network used can not use 3.party authentication like website log in, authenticators etc.**

Upload the code to your ESP32 from the Arduino IDE.
NB! **Hold down the right most button when uploading the code until you see "Connecting .." in the output terminal.** 
To monitor log data user the Serial monitor feature in the Arduino ide.