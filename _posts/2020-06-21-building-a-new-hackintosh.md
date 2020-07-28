---
layout: post
title: Building a new Hackintosh
tags: [hackintosh]
date: 2020-06-21 08:35:11 -0500
---
Oh, confusion! Welcome back friend!

I've been Hackintoshing for about 8 years now. I love the results.
The path is sometime a little convoluted, and has gotten more confusing
since the last machine I built (in 2015).

But, here we go again.

Resources: [TonyMacx86]() is my go-to. And [Amazon](). And [NewEgg]()

Hardware:
1. Gigabyte Motherboard. I don't go for the really high-end, but ...
   I want to max out ram. The newer ones have 128GB capacity.
   * [Z390 Designare](https://www.amazon.com/dp/B07K8RJZRG/?tag=tonymacx86com-20)
   has two ethernet ports, usb-c, and etc.
2. Intel processor.
   * [i7=9700F](https://www.amazon.com/gp/product/B07S8DWXT3/)
3. Memory -- I'm starting with half of MB capacity at 2x32GB, 
   * [Corsair](https://www.amazon.com/gp/product/B081BTGNDW/) or
4. Power supply, a modular one like this.    It is possible to spend a lot more money, but nah...
   * [Rosewill](https://www.amazon.com/gp/product/B00PCLGZOC)
5. Cooling. Standard, not planning to overclock (today)
   * [Intel standard fan](https://www.amazon.com/gp/product/B013U542QE)
6. Case. A blank case. I don't want leds flashing at me all the time.
   * [Antec](https://www.amazon.com/gp/product/B07LBXP8KZ)
7. Video card. I have a decent 570; do I want to buy a 580?
   * [Radeon RX 580](https://www.amazon.com/gp/product/B06Y66K3XD)
10. NVMe, motherboard attached ssd
   * [WD_BLACK](https://www.amazon.com/Black-SN750-NVMe-juego-interno/dp/B07TM6HQ3F/)
8. Monitors. Hah!
9. Keyboard, mouse, etc. Hah!
---
[install for this mb on tonymacx86](https://www.tonymacx86.com/threads/success-gigabyte-designare-z390-thunderbolt-3-i7-9700k-amd-rx-580.267551/)

---
* install emacs
  * https://emacsformacosx.com/emacs-builds/Emacs-26.3-universal.dmg
* install xcode and its command line tools
* install homebrew
  * /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install.sh)"
  * brew install wget
  * brew install id3v2
  * brew install pianobar
  * brew install imagemagick
  * brew install iperf3
  * brew install frotz
  * brew install gawk
  
