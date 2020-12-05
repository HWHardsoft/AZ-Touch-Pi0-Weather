# compile and use the drivers

we've created special overlay drivers you can copy this drivers to the directory /boot/overlays via 

## Raspbian Buster

```bash
sudo cp -f rpi-display.dtbo /boot/overlays
``` 

in /boot/config.txt, add in the following at the bottom

```bash
# TFT display and touch panel
dtoverlay=rpi-display
dtparam=rotate=0
``` 

change /boot/cmdline.txt to add the following to the end of the existing line

```bash
fbcon=map:10 fbcon=font:VGA8x8 logo.nologo
``` 


## Raspbian OS

```bash
sudo cp -f aztouch-display.dtbo /boot/overlays
``` 

in /boot/config.txt, add in the following at the bottom

```bash
# TFT display and touch panel
dtoverlay=aztouch-display
dtparam=rotate=0
``` 

change /boot/cmdline.txt to add the following to the end of the existing line

```bash
fbcon=map:10 fbcon=font:VGA8x8 logo.nologo
``` 

## compilation of driver

If you want to add changes to the driver you have to change the source code. To recompile the sources call

```bash
dtc -@ -I dts -O dtb -o aztouch-display.dtbo aztouch-display-overlay.dts
```

