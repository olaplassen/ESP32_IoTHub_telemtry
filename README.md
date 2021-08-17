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

Install the Azure IoT C SDK libraries:

Install the following libraries through the Arduino IDE Library Manager:
AzureIoTHub, AzureIoTUtility, AzureIoTProtocol_MQTT, AzureIoTProtocol_HTTP

## Run the sample
Enter the following information in:
[config.h](https://github.com/olaplassen/ESP32_IoTHub_telemtry/blob/main/iot_configs.h)
- IOT_CONFIG_WIFI_SSID(wifi name)
- IOT_CONFIG_WIFI_PASSWORD(wifi password)
- DEVICE_CONNECTION_STRING(primary connection string from iothub device) <br />
NB! The wifi network used can not use 3.party authentication like website log in, authenticators etc. 

- Upload the code to your ESP32 from the Arduino IDE.
- To monitor log data user the Serial monitor feature in the Arduino ide.