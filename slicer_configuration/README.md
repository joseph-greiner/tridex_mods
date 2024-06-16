Here is the configuration I use for Prusa Slicer 2.7 and Orca Slicer 2.0

# Update for June 16, 2024<br>
Added Orca Slicer profiles for Primary, Copy, and Mirror modes. Hopefully the filament profiles are included. These are basic settings and get me good prints on my machine while using my printer configuration. Useable as-is or as a base for modifying for your machine.

# Update for April 23, 2024<br>

Corrected copy and mirror mode start g-code to align with new print_start macro. Will no longer get errors when using these modes.<br>

Primary mode start g-code:<br>
<pre>
; M190 S0
; M109 S0 ; uncomment to remove set & wait temp gcode added automatically after this start gcode
print_start print_mode="PRIMARY" t0_starting_temp={first_layer_temperature[0]} t1_starting_temp={first_layer_temperature[1]} ooze_prev={ooze_prevention} initial_tool={initial_extruder}
</pre>

Copy mode start g-code:<br>
<pre>
; M190 S0
; M109 S0 ; uncomment to remove set&wait temp gcode added automatically after this start gcode
print_start print_mode="COPY" t0_starting_temp={first_layer_temperature[0]} t1_starting_temp={first_layer_temperature[1]} t0_printing_temp={temperature[0]} t1_printing_temp={temperature[1]}
</pre>
<br>

Mirror mode start g-code:<br>
<pre>
; M190 S0
; M109 S0 ; uncomment to remove set&wait temp gcode added automatically after this start gcode
print_start print_mode="MIRROR" t0_starting_temp={first_layer_temperature[0]} t1_starting_temp={first_layer_temperature[1]} t0_printing_temp={temperature[0]} t1_printing_temp={temperature[1]}
</pre>
<br>


It has 3 Tridex printers,
Primary mode, Copy mode, and Mirror mode. All have 0.4 nozzles, the only change is the start gcode and custom tool change gcode.

The bed size is 300x300. Adjust for your bed size.

There are two print profile, Quality and Speed.

bed_textures contains the images I use in Prusa Slicer for my bed textures. The PNG files are what you should use in Prusa Slicer, the SVG files are the editable source files for the textures that can be easily edited in Inkscape.

Updated December 4, 2023
