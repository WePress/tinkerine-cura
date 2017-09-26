## Settings for using Cura with our Tinkerine Printer

First download and install Cura. 
** [Cura Software](https://ultimaker.com/en/products/cura-software) **

Go to `Settings > Printer > Add Printer...` in the top menu bar and click on  **Custom** and then **Custom Printer** and then press the **Add Printer** button. Fill in the Machine settings listed below and then press the **Finish** button.

## Machine Settings

**X (Width)** `220 mm`

**Y (Depth)** `165 mm`

**Z (Height)** `220 mm`


**Gcode flavor** `Marlin`


**Material Diameter** `1.75 mm`

**Nozzle Size** `0.35 mm`


**Start Gcode**

```
;Sliced with Tinkerine Suite version 2.0
M104 S220
T0
G28
G90
M106 S0
G92 E0
G1 Z0.5 F2000
M109 S230.000000
G1 Z0.2 E0 F2000
G1 X65 E7 F1500
G1 X12 Y2 E14 F1500
G92 E0
```


**End Gcode**

```
;End GCode
M104 S0                     ;extruder heater off
M140 S0                     ;heated bed heater off (if you have it)
G91                                    ;relative positioning
G1 Z0.2 E-4 F2000 ;move Z up a bit and retract filament even more
G4 P600 ; dwell time of 900 ms
G28 X0 Y0                              ;move X/Y to min endstops, so the head is out of the way
G91; use relative
G1 Z80 F3000; drop 80mm
M106 S0; turn off fan
M84                         ;steppers off
G90                         ;absolute positioning
```


## Cura Profile for PLA Filament

Go to `Settings > Profiles > Manage Profiles...` in the top menu bar and then click the **Import** button and choose the `TINKERINE_PLA.curaprofile` file from this repository.
