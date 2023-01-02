

Oil Tank Level Sensor

This project uses an ESP8266 microcontroller flashed with MicroPython to monitor the level of oil in a tank. The level is measured using an HC-SR04 ultrasonic sensor, and the data is published to the Internet of Things (IoT) platform Thingspeak.com.

Getting Started
To set up this project, you will need the following:

An ESP8266 microcontroller
An HC-SR04 ultrasonic sensor
A computer with the python 3 installed
An account on Thingspeak.com
Connect the HC-SR04 ultrasonic sensor to the ESP8266 according to the following schematic:
Copy code
HC-SR04 pin 1 (VCC) -> ESP8266 3.3V pin
HC-SR04 pin 2 (Trig) -> ESP8266 GPIO pin 12
HC-SR04 pin 3 (Echo) -> ESP8266 GPIO pin 14
HC-SR04 pin 4 (GND) -> ESP8266 GND pin
Flash the ESP8266 with the MicroPython firmware using the Arduino IDE and the ESP8266 add-on.

Create a new channel on Thingspeak.com and obtain your channel's API key.

Create a new file on the ESP8266 called "secrets.py" and add the following lines, replacing "YOUR-API-KEY" with your Thingspeak API key:

Copy code
api_key = "YOUR-API-KEY"
Connect the ESP8266 to your WiFi network by creating a file called "boot.py" and adding the following lines, replacing "YOUR-SSID" and "YOUR-PASSWORD" with your WiFi network's SSID and password:
Copy code
import network

sta_if = network.WLAN(network.STA_IF)
sta_if.active(True)
sta_if.connect("YOUR-SSID", "YOUR-PASSWORD")
Upload the main code file, "main.py," to the ESP8266. This file contains the code that will measure the oil tank level and publish the data to Thingspeak.
Usage
To use the oil tank level sensor, simply power on the ESP8266. The sensor will automatically start measuring the level and publishing the data to Thingspeak.com. You can view the data by logging in to your Thingspeak account and viewing your channel.

Contributing
If you would like to contribute to this project, please fork the repository and submit a pull request with your changes.

License
This project is licensed under the MIT License. See the LICENSE file for details.
