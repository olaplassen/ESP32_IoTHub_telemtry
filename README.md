# ESP32_IoTHub_telemtry

This library is a port of the Microsoft Azure IoT device SDK for C to Arduino. It is an Arduino script for ESP32 to generate IoTHub messages with telemetry data from a connected BME280 sensor.

## Prerequisites
You should have the following ready before beginning with your board:

Setup your IoT hub

Provision your device and get its credentials

Install Arduino IDE

Install the Azure IoT C SDK libraries by one of two options:

Generate the Libraries by executing the make_sdk.py script within the build_all folder, E.x.: 
<python3 make_sdk.py -o "your-output-folder">
Note: this is also currently the ONLY way to build the AzureIoTSocket_WiFi library for using the esp32.
Install the following libraries through the Arduino IDE Library Manager:
AzureIoTHub, AzureIoTUtility, AzureIoTProtocol_MQTT, AzureIoTProtocol_HTTP

## Run the sample
Enter the following information in:
[https://github.com/olaplassen/ESP32_IoTHub_telemtry/blob/main/iot_configs.h](config.h)
- IOT_CONFIG_WIFI_SSID(wifi name)
- IOT_CONFIG_WIFI_PASSWORD(wifi password)
- DEVICE_CONNECTION_STRING(primary connection string from iothub device) <br />
NB! The wifi network used cannot have 3.party authentication like website log in. 

- Upload the code to your ESP32.