---
layout: post
title: CNC Machine Notes 001
tags: cnc
date: 2020-08-21 13:35:59 -0500
---
On my cnc machine, running UCCNC with the
[UCCNC 2017 Screenset](http://www.thecncwoodworker.com/2017.html)
I maintain my offset references via this:

1. move the spindle close to x,y,z origins
2. home all
3. select g59, set zero for all axes
3. select g58, set zero for all axes
4. put reference brass rod into spindle (3/8 inch)
5. put corner block on spoilboard
5. G0X3Y3 to position the rod above the corner block
4. lower the rod close to block
2. auto zero
2. position rod to (current machine and spoilboard)
   * G0X2Y2
   * GOZ0.8
2. open the probe flyout (left of screen)
1. check "auto zero"
1. set corner distance 1
1. select +X+Y
1. close flyout
1. remove corner block
1. G0X0Y0 to verify corner of spoilboard
