# IoT - ESP32/8266 Air quality control

IoT sensor for monitoring air quality such as temperature, humidity, CO2, gas, and others.

The application is based on [ESPHome](https://esphome.io/) framework.

## Setup credentials
Before uploading applications please copy and set the `secrets` file:

```cp secrets.yaml.example secrets.yaml```

## Sensors and ESP

We are using multiple sensors for monitoring air quality:

- DHT22 - temperature and humidity sensor
- MQ-2  - gas sensor; detection of smoke, propane, butane, and other flammable gas. This sensor needs some time to warm up for correct readings
- Brightness sensor - using photoresistor also known as LDR (light-dependent resistor)
- CCS811 - CO2 estimation and volatile organic compound sensor
- MH-Z19 - CO2 and temperature sensor
- 0.96" OLED display

In our application we used ESP32 development board with display and 18650 battery holder, but any other ESP32 can be used as long it has 5 V pin or external power supply can be used.

## Wiring

| ESP32 pin | Sensor    | Sensor pin    |
| ---       | ---       | ---           |
| GPIO 4    | display   | SCL           |
| GPIO 5    | display   | SDA           |
| GPIO 15   | DHT22     | data          |
| GPIO 16   | MH-Z19    | TX            |
| GPIO 17   | MH-Z19    | RX            |
| GPIO 22   | ccs811    | SCL           |
| GPIO 23   | ccs811    | SDA           |
| GPIO 32   | brightness| signal        |
| GPIO 33   | MQ-2      | A0            |

Note that MH-Z19 and MQ-2 sensors require 5 V as input voltage. Other sensors work on 3.3 V. For supplying 5V ESP needs to be connected via USB.

## Case

As part of our project, we also created a model of a box for our unit. STL files are attached.

The sensor was created as a project to PDI 2021
