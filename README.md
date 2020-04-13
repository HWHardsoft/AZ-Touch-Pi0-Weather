# AZ-Touch-Pi0-Weather

a weather display for a raspberry pi zero and our [AZ-Touch Pi0](https://www.hwhardsoft.de/english/projects/az-touch-pi0) wall mount touch screen (ili9341 display). This project based on the  [WeatherPi_TFT](https://github.com/LoveBootCaptain/WeatherPi_TFT) project by [LoveboatCaptain](https://github.com/LoveBootCaptain)

![AZ-Touch Pi0](https://user-images.githubusercontent.com/3049858/79135621-eef4f080-7daf-11ea-97a6-8760266a50bb.jpg)

# Installation

1. Download the [latest release](https://drive.google.com/file/d/1fyo7i7ajvh9Jw3eJMkq-weTJ9HY11tWT/)
2. Unzip the downloaded file
3. Write the image to your SD card. See [here](https://www.raspberrypi.org/documentation/installation/installing-images/README.md) for details.
4. Boot your Raspberry Pi and wait for WeatherPi_TFT to start.

# Configuration

##  Wifi settings
You can follow this [tutorial](https://www.raspberrypi.org/documentation/configuration/wireless/headless.md) to setting the Wifi headless. 

or you can use a Raspberry Pi (2/3/4) connected to Ethernet via Putty and SSH:
```bash
sudo raspi-config
--> 2 Network Options
--> N2 Wi-fi
``` 

## Localisation
```bash
sudo raspi-config
--> 4 Localisation Options
--> I1 Change Locale 
--> change your language ISO-8859-1 locales
``` 
Please note you can choose under 4 Localisation Options your time zones too!

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

# Notes about 
Because the wiring of the TFT is different to the overlay rpi-display it was needed to recompile the original rpi-display overlay. You will find the changed source and the new compiled file here.

# License

This library is free software; you can redistribute it and/or
modify it under the terms of the GNU Lesser General Public
License as published by the Free Software Foundation; either
version 2.1 of the License, or (at your option) any later version.

This library is distributed in the hope that it will be useful,
but WITHOUT ANY WARRANTY; without even the implied warranty of
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the GNU
Lesser General Public License for more details.

