---
layout: post
title: Cura Setup for my ANET A8 3d Printer
tags: [cura, 3d]
---

Various Settings:
```
x 220 mm
y 220 mm
z 200 mm
rectangular
heated
marlin
xmin -75 mm
ymin -18 mm
xmax 18 mm
ymax 35 mm
gantry 55 mm
nozzle 0.4 mm
material 1.75 mm
```

Start G-Code
```
; start
G21                          ; metric values
G90                          ; absolute positioning
M82                          ; set extruder to absolute mode
M107                         ; start with the fan off
G28 X0 Y0 Z0                 ; home all three axes
G29                          ; level the bed
G1 X20 Y0 Z0.2 F3000         ; move to front left
G92 E0                       ; reset extrusion distance
G1 X200 E20 F600             ; extrude from left to right, prime nozzle
G92 E0                       ;
G1 E-2.5000 F1800            ; retract fillament
G1 Z0.450 F1000              ; raise nozzle
G1 F9000                     ;
M117 Printing...             ; tell lcd
```


End G-Code
```
M104 S0                      ; extruder heater off
M140 S0                      ; bed heater off
G91                          ; relative positioning
G1 E-1 F300                  ; retract the filament to release pressure
G1 Z+0.5 E-5 X-20 Y-20 F9000 ; move Z up a bit
G28 X0 Y0                    ; re-home x and y
G90                          ; absolute positioning
G1 X200 Y200 F9000           ; move heatbed to front
M84                          ; steppers off
M82                          ; absolute extrusion mode
```
