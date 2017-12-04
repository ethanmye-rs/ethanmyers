+++
date = "2016-08-25T17:09:14-05:00"
draft = false
title = "Piezoelectric Acoustic Leviation"
slug = 'acousticlevitation'

+++

Because tinnitus is for the old, I decided to build an acoustic levitator. Essentially, the idea is to set up a standing wave and use that to hold small objects in the air at each node. Do it at a high enough frequency and a high enough power and you can hold small Styrofoam pellets, bits of packing peanuts, etc.

The main design centers around a piezo transducer, resonant at around 40kHz (this depends on loading, coupling etc and should be tuned). This is well outside the range of human hearing; it is not outside the range of damage. You should definitely wear ear plugs or other hearing protection if you build something similar.

Driving the transducer is somewhat tricky. A sine wave is ideal, but a square wave will do. It needs to be fairly high voltage (~200V pk-pk) and at a reasonable power -- 20W would be optimal.

To do so, I've split the design into two parts. The first is a basic h-bridge designed to drive a transformer. I've included the [link](https://github.com/hasxz/ADP3120A) to a Github repo that details the construction and includes schematics for the h-bridge. To save you a click, it's composed of two half bridge drivers (originally designed for motherboard buck converters), a few passives, and 4 N channel FETs, rated for 60V at 6A e/a. This forms the first stage, producing a 24V square wave that's fed into the transformer.

As for sourcing the transformer, I'm back driving an old high power UPS transformer. I would recommend something with a 2x or 3x higher power rating than you need, transformers are built to have very, very poor characteristics outside of their specified currents and frequencies.

The second stage consists of a rectifier, capacitor and chopper. The diode prevents back flow into the transformer, and the capacitor smooths out the voltage to produce a steady 200V supply. The chopper then produces a square wave with a duty cycle as set by the controller (in this case, an Arduino). This square wave is then fed into the piezo and the chopper frequency adjusted until resonance is reached.

The Github repo also contains the code for this project, which consists of a simple Arduino sketch the manipulates ICR1 to produce two PWM signals with customizable dead-time by directly manipulating the registers. 

It's pretty cool.