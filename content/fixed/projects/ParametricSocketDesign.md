+++
date = "2020-01-10T17:09:14-05:00"
draft = false
title = "Parametric Socket Trays"
slug = 'ParametricSocket'

+++


This is a parameter driven socket tray design. It was my first time using parameters in Fusion360 (how did I do this before!?), and they proved very useful. I have quite a few sockets to take care of, so being able to generate a valid design by only punching in the new diameter is quite handy. If you've never used parameters, [this](https://www.youtube.com/watch?v=gMNGQUAtC9o) is an excellent start.

{{< youtube oVGbRHJxd_A >}}

## Why?

I do not like most socket holder sets, which hold sockets vertically. Not only are they difficult to use (can't see the size on the socket!) I think they are clumsy and far too tall. I have always preferred the snap in trays, but Harbor Freight's Pittsburgh Pro line does not come with one, and all the generic sized ones used magnets -- no positive lock like a ball detent or recessed cutout. Understandable given the variation in outer diameter between manufacturers, but not what I'm looking for.

A big factor motivating my design was extendability. I want to be able to add sockets in any order I please and be able to make additions over time. A monolithic tray won't work, so the design needs to be easily extendable.

The other factor was size -- I want to have every length 10mm socket together. I see no point in having all my short sockets together while I group my long sockets somewhere else. Designing my own system lets me fix that.

Motivated half for my edification, half by obstinateness, I designed my own using Fusion360. 

## Design

<iframe src="https://myhub.autodesk360.com/ue2ac1d01/shares/public/SH919a0QTf3c32634dcf7df40754c7ccddf4?mode=embed" width="800" height="600" allowfullscreen="true" webkitallowfullscreen="true" mozallowfullscreen="true"  frameborder="0"></iframe>

Check out the fusion iframe I placed above. It's a bit slow to load, but shows a full model. The design is yours under an MIT license as a [f3d] file for free!

The basic concept is each socket size clicks into a tray, which then sits on 8mm rail. This lets you start with just a few sockets and gradually work up to more, or fill in the gaps in a set with replacement sockets, half sizes, uncommon sizes, different manufacturers, etc. It's also more efficient with space -- the rail is only as long as you need it to be, and the 8mm rail it rides on is dirty cheap (about $3.50 a foot). The click is accomplished by setting the cylinder cut extrusion about 2mm below the top of the tray.

There's a couple of things I like about my design. The biggest is extendability -- simply pop new socket trays onto the rail, and it's good to go. I also like the click (see [video](https://www.youtube.com/watch?v=oVGbRHJxd_A)) -- it's tactile, audible, and keeps the sockets firmly seated in any orientation. The finger indents make it easy to remove the socket, and the socket cutout length is long enough to put in at any angle, while keeping long and short sockets together.

It's printed with the crappiest waterlogged PLA I could find. PETG may be a better choice for long term use, but it likely won't matter in the fairly sheltered environment of my tool chest.

## Video

{{< youtube oVGbRHJxd_A >}}

The short socket click is a little off -- it's partly because the socket cutout is a smidgen too short. You'll also notice I'm missing a bottom 8mm rail -- I'm actually using a 8mm reamer shank as a decoy. There's some wonky video artifacts too, not sure what happened there.

*2020*

[f3d]: /other/SocketTray.f3d
