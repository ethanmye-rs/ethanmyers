+++
date = "2017-12-26T17:09:14-05:00"
draft = false
title = "Decapping microchips for refunds"
slug = 'chips'

+++

I buy quite a few microchips from China over the course of any project. Whether it's jellybean parts or branded specialty parts, Aliexpress and eBay have everything imaginable for very attractive prices. That being said, the pedigree of most chips is murky at best, and given a shortage of any part, impostors peddling phony or damaged chips inevitably spring up. The only real way to check if you have the real deal is to pull the die out and check, a time consuming and honestly, kind of dangerous process. 

This entire process was kicked off upon receiving some suspicious chips from a vendor. The chips in question were marked [IR2113](https://www.infineon.com/dgdl/ir2110.pdf?fileId=5546d462533600a4015355c80333167e), which is a ±2A MOSFET gate driver. I was trying to drive a large array of MOSFETs, and the 20mA GPIO drive from my microcontroller wasn't able to switch the massive gate capacitance fast enough. The MOSFETs just ended up stuck in the linear mode and burning up, much to my chagrin. I tacked on a gate driver to my order of parts and lo and behold, it showed up about 2 weeks later. By my math, ±1.2A should have been enough to quickly get the MOSFETs into saturation. The driver I selected was good to ±2A, so no problem. However, no matter what I did, I could not get the assembly to work. No about of fiddling was getting this chip to pump out enough current to keep my MOSFETs from cooking. Frustrated, I saw [this](https://www.youtube.com/watch?v=mT1FStxAVz4) video from Applied Science, and immediately set to work. 

I found it easiest to simply sand down the chip, removing as much material as possible, then tossing the remaining bit of IC and plastic in a flask of boiling sulphuric acid. This removes the remaining epoxy coating within about an hour, and is much faster and less labor intensive than adding the acid drop wise to the package. You do need to fish the die out an acidic sludge afterwards, but this is partly remedied by copious amounts of baking soda and a flashlight under the flask.

The end result: Turns out the actual chip inside was an [IR2112](https://www.infineon.com/dgdl/ir2112.pdf?fileId=5546d462533600a4015355c81cb71685), a cheaper version of the IR2113 only rated for +200mA -420mA. No wonder nothing worked - someone along the line took a box of cheaper chips, sanded off the top, and marked a new code on top.

I used a cheap USB microscope to view the die and confirm the relabeling. Please excuse the terrible quality and dead pixels.
{{< youtube e6DfBuPwAAA >}}

You can clearly see the IR2112 marking on the left hand of the screen, around 16 seconds in.

*2017*