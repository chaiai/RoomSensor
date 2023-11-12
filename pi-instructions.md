# Raspberry Pi instructions

## OS
Raspberry Pi OS Desktop 32bit

## Software
Perform updates:

<code>sudo apt-get update && sudo apt-get -y upgrade</code>

Install build tools:

<code>sudo apt update
sudo apt -y install cmake gcc-arm-none-eabi build-essential</code>
## Pico Build Directory
<code>cd ~
mkdir -p RoomSensor
cd ~/RoomSensor
git clone -b master https://github.com/raspberrypi/pico-sdk.git
cd pico-sdk
git submodule update --init
cd ..
git clone https://github.com/carolinedunn/pico-weather-station</code>

## Modify weatherstation.c
Navigate to /home/pi/weather-station/pico-weather-station and open weatherstation.c with Geany in your File Manager to review the source code.  

Code Notes for weatherstation.c

    weatherstation.c is the main source file for our project today.
    Line 17: We set our Pico to read our DHT from GPIO15. You can set up multiple DHT’s or change your GPIO pin here.
    Line 199-200: This printf statement is for troubleshooting purposes and can only be accessed via minicom. Accessing readings via minicom will be discussed in the troubleshooting section.
    Line 202: We will display Farenheit readings in this weather station. You can change the reading to Celsius.
    Line 211: Display an updated temperature at 2 second intervals (or 2000 milliseconds).
