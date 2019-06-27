## Bone Conduction Headphones
This project is still a work in progress.
These headphones uses bone conduction technology and I plan on implementing CMU Sphinx and auto detection of if they're being used in the future.

### Hardware Required
* Raspberry Pi Zero W
* Bone conductor transducer ([Adafruit product page](https://www.adafruit.com/product/1674))
* Audio amplifier  ([MAX98306 Stereo Audio](https://www.adafruit.com/product/987))

### Raspberry Pi Zero USB SSH Set-up
To enable SSH over USB on your Pi without access to a Wifi network, you can follow instructions [here](https://desertbot.io/blog/ssh-into-pi-zero-over-usb). <br>
TL;DR <br>
* Write an empty file named `SSH` in the bootable memory card
* Add `dtoverlay=dwc2` to the bottom of `config.txt` file 
* Add `modules-load=dwc2,g_ether` after `rootwait` in `cmdline.txt`

### Enabling audio output
Raspberry Pi Zero doesn't have a 3.5mm built in, but no worries! Adafruit has a [tutorial](https://learn.adafruit.com/adding-basic-audio-ouput-to-raspberry-pi-zero/pi-zero-pwm-audio). <br>
TL;DR <br>
Add `dtoverlay=pwm-2chan,pin=18,func=2,pin2=13,func2=4` at the bottom of the `config.txt`file

### Connecting to Pi
Then connect to your Pi by typing `ssh pi@raspberrypi.local` in Terminal. `raspberrypi` is the default name of a Pi. You can use `raspi-config` to connect to wifi or change the name of your Pi.
