---
layout: post
title: 4 Monitors, 5K Wallpaper
tags:
date: 2020-06-06 15:54:27 -0500
---
I have a 4 monitor setup on my Hackintosh in my home office; two 1920x1200 monitors
on top and two 2560x1440 monitors below. I typically use at least 4 virtual 
desktops (whatever Apple calls them) and I enjoy having background images 
on them.

First, MACOS does not directly support filling all monitor space with
a single large image with that image split across the monitors. It will
happily duplicate a scaled version on each monitor, but you still have
to set each monitor up separately.

Second, with four monitors and 4 (or 5, or 6) desktops, 
**that's a lot of settings to do with the mouse** .

Third, images big enough to cut into four parts like that are (relatively)
difficult to find. Not quite exact, but 5120x2880 isn't too hard to find.
I found a pool of them to swim in at [HDWALLPAPERS](https://www.hdwallpapers.in/) .
I favor darker nature backgrounds, no people, no very light areas. They had a good 
selection in both style and resolution.

After downloading a handful of them, what to do about problems 1 and 2?

First, a command line utility called ```wallpaper``` (duh) by Sindre Sorhus, 
available on both 
[github](https://github.com/sindresorhus/macos-wallpaper) as source and from [homebrew](https://brew.sh/) as an installable command line item.

Thanks Sindre!

This utility will 
* enumerate the available screens
* allow a command line to set the desktop image for an individual screen

Second, [ImageMagick](https://imagemagick.org/index.php) manipulates
images like nobody's business.

Finally, taking all of that and putting it together in a stupid shell
script (I'm not a shining star, I just have a club to hit the shell with),
I can execute a script, break a large image into 4 small bits per my 
system geometry, and set all four backgrounds.  All from a single command!

```
#!/bin/sh
x=`ls -1 |shuf -n 1`
echo $x

if [ ! -f temp/ul_$x.png ]; then

convert -size 5120x2880 -extract 1920x1200+0640+0000 $x temp/ul_$x.png
convert -size 5120x2880 -extract 1920x1200+2560+0000 $x temp/ur_$x.png
convert -size 5120x2880 -extract 2560x1440+0000+1200 $x temp/ll_$x.png
convert -size 5120x2880 -extract 2560x1440+2560+1200 $x temp/lr_$x.png

fi

wallpaper set temp/ul_$x.png --screen 1
wallpaper set temp/ur_$x.png --screen 3
wallpaper set temp/lr_$x.png --screen 0
wallpaper set temp/ll_$x.png --screen 2

```

Thanks to all the resources that contributed to my little effort!

