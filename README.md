jam-stapl for Raspberry Pi 4
============================

This is a fork of https://github.com/margro/jam-stapl repository adding support for Raspberry Pi 4.  
This version is using **wiringPi** library (version >= 2.52), but should
easily work on other Raspberry Pi versions.

Installing wiringPi 2.52
========================

The winingPi shipped with your Linux version my be to old.  
We need wiringPi version **2.52** or higher.

1. Check current version
```
gpio -v
```

2. If version < 2.52, remove current version
```
sudo apt purge wiringpi
```

3. Download and install new version
```
mkdir tmp
cd /tmp
wget https://project-downloads.drogon.net/wiringpi-latest.deb
sudo dpkg -i wiringpi-latest.deb
```


Original README
===============

Altera Jam STAPL Player with support for 64-bit Windows versions.

Changes with respect to v2.5 from Altera:
  * VS2013 solution added (for 32-bit and 64-bit builds)
  * Uses the Inpout32 driver library (v1.5.0.0) for parallel port access. (See also http://www.highrez.co.uk/Downloads/InpOut32/)
  * Raspberry Pi (Linux) support added

**Windows:**
Run jam.exe the first time with administrator permissions to install and load the Inpout32 driver.

**Raspberry Pi:**
Uses the following pins for JTAG programming:
  * TCK = Bcm GPIO 7, P1 pin 26 (out)
  * TDI = Bcm GPIO 8, P1 pin 24 (out)
  * TMS = Bcm GPIO 25, P1 pin 22 (out)
  * TDO = Bcm GPIO 24, P1 pin 18 (in)
For different pins, change the defines in jamgpio.c