# IOT LED Example for WEMOS ESP8266  ESP-WROOM-32

This repository is from one of the laboratory sessions for Introduction to Computers and Informatics of TTU CyberSecurity Engineering

Details:
https://wiki.itcollege.ee/index.php/Category:I600_Introduction_to_Computers_and_Informatics#Assignment:_Set_up_basic_IoT_scenario

# Requirements:
Python 3.x

Running:
First clone the repository to your computer via Git. Following commands are for Linux, Mac and Windows.

```sh
git clone https://github.com/kenny007/IoT-Server.git
cd IoT-Server
```

On your machine

Run ``` main.py ``` like

python main.py
then browse to http://localhost:8080/

## On WEMOS

Run following command:

```sh
sudo ampy -p /dev/ttyUSB0 put main.py 
```

# Troubleshooting

## Resetting Device

If at any point your device stops resposnding, you may need to reset and reflash it.

The instruction below applies for different chipsets check what is written on chipset to know which to use:

esp32:

```sh
wget http://micropython.org/resources/firmware/esp32-20171017-v1.9.2-279-g090b6b80.bin
sudo esptool.py -p /dev/ttyUSB0 -b 460800 erase_flash
sudo esptool.py -p /dev/ttyUSB0 -b 460800 write_flash --flash_mode dio 0x1000 esp32-*.bin
```
esp8266:

```sh
wget http://micropython.org/resources/firmware/esp8266-20170612-v1.9.1.bin
sudo esptool.py -p /dev/ttyUSB0 -b 460800 erase_flash
sudo esptool.py -p /dev/ttyUSB0 -b 460800 write_flash 0 esp8266-*.bin
```