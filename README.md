# SSD1306 OLED Display

This plugin utilizes a 128x32 SSD1306-based display to display printer and job status for OctoPrint.  It provides a convenient way to view job status directly on the Raspberry Pi without needing to open a web page, for printers that either don't have a display or won't respond to commands to update their display.

This has been re-written from the forked repository. It's written for a 128x32 display and adapted to Python 3.

## Setup

Install via the bundled [Plugin Manager](https://docs.octoprint.org/en/master/bundledplugins/pluginmanager.html)
or manually using this URL:

    https://github.com/fredrikbaberg/OctoPrint-SSD1306/archive/main.zip

### Libraries
Install the following libraries.
```
sudo apt install -y python3-dev python-smbus i2c-tools python3-pil python3-pip python3-setuptools python3-rpi.gpio
```

## Configuration

### Enable I2C in Raspberry config
```
sudo raspi-config
reboot
```

### Check I²C SSD1306 OLED Display dectection
With the I2C libraries installed I used the i2cdetect command to find the module on the I2C bus.
OLED Display is at address 0x3C.

```
pi@OctoPi:~ $ i2cdetect -y 1
     0  1  2  3  4  5  6  7  8  9  a  b  c  d  e  f
00:          -- -- -- -- -- -- -- -- -- -- -- -- --
10: -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- --
20: -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- --
30: -- -- -- -- -- -- -- -- -- -- -- -- 3c -- -- --
40: -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- --
50: -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- --
60: -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- --
70: -- -- -- -- -- -- -- --
```
