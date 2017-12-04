+++
date = "2016-08-25T17:09:14-05:00"
draft = false
title = "ESP-12 Programming Jig"
slug = 'esp12jig'

+++

I’m building a small product the uses the ESP8266 chipset to enable mesh networking between a variety of devices. However, I need a way to program them initially, before they go onto the carrier PCB that contains power + peripherals. It’s a pain to try and breadboard or deadbug the 7 or so connections needed to flash new firmware, and both require soldering, something I’m trying to avoid, as they will be soldered in the final assembly and I’d like to reduce potential sources of failure.

What I’ve built to solve this problem is a general purpose programming jig using pogo pins and 3D printed parts. It holds the ESP-12 on a bed of pogo pins (also called a bed of nails) and allows the programmer to make reliable contact with all necessary pins merely by pressing down.

I’m using a cheap USB to UART converter based on the CP2102. It and it’s ilk are dirt cheap and ubiquitous on eBay/Aliexpress/Taobao and come in several variants, but as long as there’s TX, RX, GND and 3.3V connections, it should work fine.

I’m also using platformio as a toolchain manager. It’s incredibly convenient to use as a CLI utility and makes compiling and uploading new firmware a breeze, even for a variety of platforms (AVR/PIC/MSP/ESP etc).