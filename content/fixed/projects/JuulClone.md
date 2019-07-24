+++
date = "2017-12-26T17:09:14-05:00"
draft = false
title = "Copying Juul Pods"
slug = 'juulpods'

+++

# Background

Vaping, for better of worse, has supplanted smoking. It's *probably* less dangerous for you, but the addictive kick still remains.

Chief among the new purveyors of vape is a company called [Juul](https://www.juul.com/). They make the eponymously named Juul, a device of which anyone under 18 is innately familiar with. They've got this clean, undeniably sleek, Johnny-Ive-would've-loved-it dark anodized aluminum aesthetic -- and they're covert to boot. They take a single serve, Keurig-inspired pod, and fill it with proprietary liquid, containing a whopping [59mg](https://support.juul.com/home/learn/faqs/juulpods-juulpod-liquid) of nicotine -- about as much as a pack of cigarettes. This sort of convenience + highly addictive product + borderline targeting of young people is what made Juul explode, an makes investors wet their pants.

Juul, which raised some [$110 million](https://www.cnbc.com/2017/12/19/juul-labs-raising-150-million-in-debt-after-spinning-out-of-pax.html), is not out to make smoking any less expensive. Their business model is not unlike printer ink -- give the device away for free, then charge through the nose for pods. Those little pods, containing a mere 0.7ml of liquid, retail for about $4 a piece (for reference, this works out to about $15,000 per gallon of liquid). What is worse, these pods are an impressive bit of manufacturing, but are not reusable. That being said, there is no real reason for these pods to be so expensive, so I decided to reverse engineer them, mostly to satisfy my idle curiosity.

# Chemistry

E-Liquid/vape juice is basically a mix of vegetable glycerin (VG) and propylene glycol (PG) plus nicotine plus flavoring and some other secret sauce ingredients. Both VG and PG are common food additives used as humectants in a stunning variety of food products, from cookies to cakes to Twinkies.

Juul's technical innovation, if you can call it that, is in the nicotine. They've figured out how to pack **very** high doses of nicotine into very small amounts of e-liquid. However, doing this isn't easy with a freebase form of nicotine -- a high concentration of freebase nicotine is apparently extremely harsh and unpleasant to smoke. Doses of more than 10mg/mL would be unusable for most. What Juul figured out was the conversion of the freebase form into a salt form -- not unlike turning crack into cocaine. In fact, it's actually the *exact same* fundamental process, albeit dressed up with slightly different chemicals. Essentially, we are taking the freebase form of nicotine and using an acid to turn it into a salt. The pure (freebase form) amine is slightly basic, so the addition of acid results in an acid-base reaction, making the nicotine salt. This salt will be easier to absorb as well as negating the "harsh" effect of high nicotine content. 

The specifics of this are pretty interesting. We need a couple of things. The first is a water soluble, food safe, high (>200C) decomposition temp, low cost commercially available acid. Juul mentions most of the good ones in the patent, and even a couple that cannot conceivably work. 

I decided to delve into Juul Pods to address two big issues: waste and nicotine concentration. In terms of waste, these little pods are everywhere, so much so that the [reddit.com/r/whatisthisthing](https://www.reddit.com/r/whatisthisthing/) logo is a Juul pod. In terms of nicotine concentration, I think Juul labs has done a disservice to people attempting to use the device to quit. It is straightforward to build a 18 week program to decrease the nicotine content without the user noticing too much. However, this obviously goes against their business interests, and they will not do so, even as they market it as a better smoking alternative.

##### Disclaimer

Juul has patented this idea, and the patent covers a wide variety of acids and PG/VG mixes. In publishing this information, I believe this falls under the research exemption provided for patents. I have no profit motive -- just idle curiosity. If you're interested in making some Juul pod juice, I've laid out several formulations that I believe are about 80 to 90% there, and can be infinitely tweaked.


# Practice


You'll need quite a bit of equipment, but a majority of it is low cost. total BOM, including tools, should come to less than $75.

Item | Cost 
-----|------
 Pipetman or volumetric pipette   | $26
 Small beaker or glass test tube  | $4.88
 milligram scale 				  | $11.50
 Nicotine solution 			      | $12.59
 flavoring						  | $6
 PG/VG 						      | $8.99
 Distilled Water				  | $0.59 
 Your choice of acid      	      | $10 |eBay / Amazon



I've found this recipe to be fairly satisfactory, but I went through approximately ~10 different formulations before finding something good. 

	1000uL VG Nicotine Solution 48mg/mL
	0.08g Sodium Benzoate
	100uL Berry Flavoring
	300uL Vegetable Glycerin

You'll want to make sure you fully mix all ingredients. You can warm up the solution to decrease viscosity and enable easier mixing. This should make enough to fill one Juul Pod, plus some extra that will invariably coat the test tube and glass.

# Going Forward

I don't actually vape, so this isn't a project I'll be pursing in the future. However, I think there are several avenues worth pursuing. Notably -- synthetic nicotine, which lacks the impurities that affect flavor in commercially available extracted nicotine (letting you dial up nicotine content even farther), compound acid mixtures (i.e, a mixture of malic acid and benzoic acid), reduced nicotine levels, novel carriers, etc.

*2017*