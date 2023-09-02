![Better print start](/PrintStart/printstart.mov)

# Print start GCODE

I like Prusa MK4 print start, which extrudes a lot of filament in short time thus really getting rid of the strings and gunk thats on the nozzle from previous print. So I have accomodated it to be used for Voron0.

```
[gcode_macro PRINT_START]
gcode:
    {% set BED_TEMP = params.BED_TEMP|default(60)|float %}
    {% set EXTRUDER_TEMP = params.EXTRUDER_TEMP|default(200)|float %}

    M107                         # fans off

    M140 S{BED_TEMP}             # start bed heating
    M104 S140                    # start nozzle temp to 140

    G28                          # home axes
    G90                          # abs pos
    G1 X10.0 Y10.0 F3000         # move up front

    M190 S{BED_TEMP}             # wait for bed to reach temperature
    M109 S{EXTRUDER_TEMP}        # wait for nozzle to reach temperature

    # Extrude purge line (MK4 style)
    M83                          # extruder relative mode
    G0 X3 Y3.0 Z15 F3000         # move away and ready for the purge
    G92 E0                       # reset extruder position
    #G1 E2 F2400                  # deretraction after the initial one before nozzle cleaning
    G0 E7 X15 Z0.2 F500          # purge
    G0 X25 E4 F500               # purge
    G0 X35 E4 F650               # purge
    G0 X45 E4 F800               # purge
    G0 X{45 + 3} Z{0.05} F10000  # wipe, move close to the bed
    G0 X{45 + 3 * 2} Z0.2 F10000 # wipe, move quickly away from the bed
    G92 E0
```

For this to work, you will also have to adjust `max_extrude_cross_section` under `[extruder]` section. I've set mine to **30.0**:

```
[extruder]
...
max_extrude_cross_section: 30.0
...
```

In slicer, simply call PRINT_START with two parameters (first layer bed temp and first layer nozzle temp). Example for OrcaSlicer:

```
PRINT_START EXTRUDER_TEMP=[nozzle_temperature_initial_layer] BED_TEMP=[bed_temperature_initial_layer_single]
```
