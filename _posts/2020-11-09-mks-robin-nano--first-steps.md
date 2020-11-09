---
layout: post
title: MKS Robin Nano -- First Steps
tags: Marlin "Robin Nano"
date: 2020-11-09 10:57:50 -0600
---
I bought a [Creativity Elf CoreXY](https://www.amazon.com/gp/product/B086X2989N) 3d printer. The stock photo is not quite what I have, but very close (mine has
a bowden extruder instead of a direct extruder)

![elf](/img/CreativityElf.png)

Really good price, good features, easy assembly, and decent prints right
out of the box.

![bunny](/img/bunny.png)

!<img src="/img/bunny.png" width="200" />

However, and a pretty big one for me, was that the firmware in the printer
was closed. This in spite of the fact that it is based on and even acknowledges
the [Marlin](https://marlinfw.org/) project.

So, the adventure begins here.

The embedded brain of the printer is
[MKS Robin Nano 1.2](https://github.com/makerbase-mks/MKS-Robin-Nano-V1.X).
MKS has recently open-sourced the hardware and software for this, but
the information is pretty sketchy in a lot of places.

Creativity offers an upgrade to the firmware on their website, but I
have reservations. The printer already works and if I do the SD-card
update I will lose the current firmware -- there is no apparent way
to read it out of the Robin Nano to archive it and restore it. So I ordered
a spare Robin Nano and its TFT display to play with.

Next, I will configure, compile, and load Marlin on it.


