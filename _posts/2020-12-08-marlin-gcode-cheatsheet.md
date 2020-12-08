---
layout: post
title: Marlin GCODE Cheatsheet
tags: Marlin
date: 2020-12-08 09:06:57 -0600
---
The GCODE I use a lot

| GCODE | Description | Example |
| G91 | set relative mode | |
| G90 | set absolute mode | |
| G92 | set position | G92 E0 |
| G0 | move axis to position | G0 F200 E20 |
| M500 | save parameters to eeprom ||
| M503 | report in-use eeprom parameters ||
| M302 S0 | enable cold extrusion | |
| M119 | endstop states ||
| M120 | enable endstops ||
| M121 | disable endstops ||
| M122 | TMC Stepper debug info ||
| G34 | synchronize z axis motors ||
| G28 | home all ||
| G29 | level bed ||
| M600 | filament change ||
| M603 | configure filament change load/unload length | M603 L1000  U1050 |
| M701 | load filament ||
| M702 | unload filament ||
