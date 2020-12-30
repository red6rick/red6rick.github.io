---
layout: post
title: Power Switch for Raspberry Pi
tags:
date: 2020-11-08 09:31:29 -0600
---


|   name                 | pin  |   pin  |   name               |
|   3.3v DC Power        |   1  |     2  |   5v DC Power        |
|   GPIO02 (SDA1, I2C)   |   3  |     4  |   5v DC Power        |
|   GPIO03 (SCL1, I2C)   |   5  |     6  |   Ground             |
|   GPIO04 (GPIO_GCLK)   |   7  |     8  |   GPIO14 (TXD0)      |
|   Ground               |   9  |    10  |   GPIO15 (RXD0)      |
|   GPIO17 (GPIO_GEN0)   |  11  |    12  |   GPIO18 (GPIO_GEN1) |
|   GPIO27 (GPIO_GEN2)   |  13  |    14  |   Ground             |


~~~~
                 330           |\ |
   pin 7.-------/\/\/\/--------| \|---------o---- pin 9
   gpio 4                 long | /|         |     gnd
                           leg |/ |         |
                                      /     |
   pin 5 ----------------------------/ -----+
   gpio 3

~~~~

Then add to /boot/config.txt

~~~~
# enable shutdown
dtoverlay=gpio-shutdown
gpio=4=op,dh
~~~~

That's it! Press the button once to turn pi on; the LED will light.
Press again to turn pi off; LED will turn off!

Magic!!!

Thanks to Jeremy S. Cook at

https://www.embedded-computing.com/guest-blogs/raspberry-pi-power-up-and-shutdown-with-a-physical-button

