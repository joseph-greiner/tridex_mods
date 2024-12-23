Here is the configuration I use for Prusa Slicer and Orca Slicer

# Update for December 20, 2024
Updated the slicer profiles to current releases.<br>
<ul>
    <li>Prusa Slicer: Removed custom gcode on tool change. Prusa Slicer no longer supports wipe tower location placeholders as of version 2.9.0 Alpha.</li>
    <li>Orca Slicer: Updated hacked single tool multimaterial printer to multiple tools. I will add Orca version numbers on the zip file from now on.</li>
</ul>

# Update for June 16, 2024<br>
Added Orca Slicer profiles for Primary, Copy, and Mirror modes. Hopefully the filament profiles are included. These are basic settings and get me good prints on my machine while using my printer configuration. Useable as-is or as a base for modifying for your machine.<br>

When using Copy and Mirror modes, make sure the second filament is the same as what you have in the printer, if set to one filament then it will use that for both extruders.

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
