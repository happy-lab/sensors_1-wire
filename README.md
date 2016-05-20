# Publish One-Wire Sensor Data to MQTT
This service collects data from an One-Wire sensor network and publishes
them to a MQTT server.

## Status
This project is historical.  The One-Wire sensor networks are being replaced
by alternatives based on **XBee**, **ESP8266** and ...  Many of the companies
manufactoring One-Wire boards have ceased operations. 

## License
This program is released under a MIT [license](./LICENSE).

## Implementation
All program are written in Python 3 and require that the
[Python MQTT package](https://pypi.python.org/pypi/paho-mqtt/1.1) and the
[Python OWFS client library for owserver protocol](https://pypi.python.org/pypi/pyownet)
be installed.  The program was developed and tested on **Arch Linux**
systems running on ARM processors and a Fedora 23 system.

## Installation
* Install and configure a MQTT server or use a public service.
* Install the OWFS Client Library
	* `pip install pyownet`
* Install the MQTT Client
	* `pip install paho-mqtt`
* Copy the program to the desired directories or run `makepkg` and install with **pacman**.
* Modify the **owfs** configuation file and place in `/etc/owfs.conf`
* Modify the **sensor_1-wire** configuation file and place in `/etc/sensor/sensor_1-wire.conf`
* Enable the services:
	* `systemctl enable owserver`
	* `systemctl enable sensors_1-wire`

## Things To Do
* Change running user to non-root.
* Support MQTT authentication
* Support secure MQTT connections
* Better documentation.
