# AZ-Touch-Pi0-Weather

a weather display for a raspberry pi zero and our [AZ-Touch Pi0](https://www.hwhardsoft.de/english/projects/az-touch-pi0) wall mount touch screen (ili9341 display). This project based on the  [WeatherPi_TFT](https://github.com/LoveBootCaptain/WeatherPi_TFT) project by [LoveboatCaptain](https://github.com/LoveBootCaptain)

![AZ-Touch Pi0]()

# Installation
============

1. Download the [latest release](https://drive.google.com/file/d/1fyo7i7ajvh9Jw3eJMkq-weTJ9HY11tWT/)
2. Unzip the downloaded file
3. Write the image to your SD card. See [here](https://www.raspberrypi.org/documentation/installation/installing-images/README.md) for details.
4. Boot your Raspberry Pi and wait for WeatherPi_TFT to start.

# Configuration
==============
It's recommend to use a Raspberry Pi 2, 3 or 4 connected to Ethernet for the steps 4

##  Wifi settings
sudo raspi-config
--> 

## Localisation
sudo raspi-config


## Darksky Weather account
get an api key from darksky / forecast.io:

* go to [darksky.net](https://darksky.net/dev/)
* and register to get an API key

## Edit config file
```bash
cd
cd WeatherPi_TFT
sudo nano config.json
```
* replace `xxxxxxxxxxxxxxxxxxxxxxxxx` in  `"FORECAST_IO_KEY": "xxxxxxxxxxxxxxxxxxxxxxxxx"` with your own API key
* replace `en` in `"FORECAST_LANGUAGE": "en"` with your preferred language
* replace `si` in `"FORECAST_UNITS": "si"` with your preferred unit format
* replace `40.705565` and `-74.1180865` in `"FORECAST_LAT": 40.705565` and `"FORECAST_LON": -74.1180865` with the coordinates of your preferred forecast-location (this example-location data is from new york city)
* replace `flags` in `"FORECAST_EXCLUDES": "flags"` with whatever you want to exclude in the API-respond
* for language-support, units, lat , lon and excludes please refer to -> **[DarkSky API Docs](https://darksky.net/dev/docs/forecast)**

reboot your Pizero!
```bash
sudo reboot
```


