+++
date = "2016-08-25T17:09:14-05:00"
draft = true
title = "LED Growlights"
slug = 'growlights'

+++

I happen to grow a few plants, none of which are marijuana, and wanted to have a way to keep them alive through the winter. Thus, I set out to build some grow lights.

I considered using HPS/MH, but had no desire to change bulbs or buy an expensive driver. I also wasn’t a fan on the point source illumination, wanting to spread out the output evenly over a range of plants, or the high amount of heat generated. Plus, LEDs are cool and purple.

I could have bought a pre-built LED growlight, but was disappointed by what I saw as pseudo-scientific claims on the low end lights, outright lying about specs throughout most of the industry, and inflated prices. There are some notable exceptions, but a vast majority of what you see on eBay, Aliexpress and Amazon is garbage.

That being said, I decided to build my own.

I started with a few 3W LEDs – the kind you can find on eBay or Aliexpress for a few cents a piece. They really aren’t 3W (at best, about 2W) and for any sort of reasonable efficiency, shouldn’t be driven at anywhere near their rated value. They’re not nearly as efficient at their rated current, and more difficult to cool. If you trust the spec sticker, these LEDs should top out at around 120 lm/w, but it’s probably a bit lower in reality.

I chose a mixture of red and blue LEDs, mainly based on price. I could find little credible evidence that anything outside of the viable spectrum had a significant affect on growth, so there are no UV or IR LEDs in this build either. UV/IR aren’t nearly as developed as red or blue, so I probably would not include them either way.

If you’re looking to build your own, make sure the LEDs you buy do not have a phosphor (white LEDs being the exception). Those LEDs are just blue LEDs with a phosphor that shifts the wavelength to something longer than blue – red, yellow, green, etc. The issue is efficiency, which is now shot, and the reason LEDs were chosen in the first place.

As for the PCB, I chose a aluminum backed one. This allows me to pull more heat out of the LEDs quicker, improving efficiency and increasing lifespan. Many of the high end LED manufacturers use this technique, while some of the lower cost ones will simply use a regular FR-4 PCB with a gigantic ground plane. I chose several originally designed for LED tube lights, but they also work well for this application.

Ultimately, I was making such a small number of boards that I couldn’t afford to get my own made up on aluminum. Luckily, I found a seller on Taobao with strings of around 10 in series. Due to LEDs nonlinear IV curve, strings in parallel often fail, even when they’ve been carefully balanced, so putting the LED strings in series, each with their own driver, was a must.

LED drivers in my power and voltage range are comparatively expensive to buy, so I initially built my own. It was fairly basic – a comparator drove a MOSFET, and a sense resistor provided the feedback to compare against. It ran at a fairly high frequency, mainly limited by the comparator’s ability to oscillate and a small cap intended to prevent >1 MhZ oscillations. A voltage divider set the current. The schematic was drawn up on a receipt, but if there’s any interest, I could bang something out in Eagle.

After building a demo, I looked having it fabricated. All in all, it would have cost around $4 to $5 to buy the PCBs and parts. There would have been a non-zero labor time as well, including setting it up, troubleshooting, and fixing errors. I would also need a high-ish voltage DC source, adding to the cost.

Incidentally, I was looking around Aliexpress for parts when I stumbled across old TV back light drivers. These were perfect – around I_max of ~0.5A, up to 85V, and best of all, super low cost, around $2 in singles. They were based around a dirt cheap specialty boost chipset which promised “PWM” dimming and an enable switch, and took a standard 12-24V. Not only was it a better driver design, but it also cost less. So I ditched my own prototypes and ordered several. It’s possible to pull approximately 40W out of them, and they drive the LEDs very well. It’s enabled with a 5V signal, which I’m using a 5V zener to provide. I haven’t been able to find out much about the PWM dimming, and am still looking into it. (0-3.3V? 0-5V? 0-10V, analog?) I’m betting 0-5V, but still looking for a non-restricted datasheet.