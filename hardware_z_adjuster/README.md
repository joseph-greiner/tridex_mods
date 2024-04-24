# Hardware z adjustment using double tap

This small modification adds hardware adjustable z height adjustment for the T1 carriage. My testing has shown it to be very consistent, even after travelling across hundreds of miles of US interstate.

## Requirements:

<ul>
  <li>The <a href="https://github.com/joseph-greiner/Double-TAP-for-Tridex">Double Tap for Tridex</a> carriages.
  <li>The tap upper for D2HW available <a href="https://github.com/VoronDesign/Voron-Tap/blob/main/STLs/Tap_Upper_D2HW_r8.stl">here</a>, installed on the the T1 tap front.</li>
  <li>The nozzle for T1 MUST be physically lower (closer to the bed) than the nozzle for T0. If your T1 nozzle is higher than T0, you can shim your hot end with a small printed part from above the heat sink, or a metal washer from below. I personally use an M4 washer between the nozzle and heat sink on my Revo setup, the spring that holds the heater keeps it trapped and not falling out if care is taken.
  <li>3 pieces of hardware you probably already have.</li>
</ul>

## Bill of Materials:
<ul>
  <li>1 - M3 heat set insert.</li>
  <li>1 - M3x12 SHCS.</li>
  <li>1 - M3x20 SHCS.</li>
  <li>Printed parts. ABS / ASA recommended, standard Voron print settings.</li>
</ul>

## Instructions:
<ul>
  <li>Install the heat set into the shuttle piece, from the large side.<br>
    <img width=200 src="https://github.com/joseph-greiner/tridex_mods/blob/main/hardware_z_adjuster/images/assy_1.png">
  </li>
  <li>Screw the M3x20 fully into the housing, and continue rotating it until it rotates without too much resistance. Basically create some threads with the screw and then strip them out.<br>
    <img width=200 src="https://github.com/joseph-greiner/tridex_mods/blob/main/hardware_z_adjuster/images/assy_2.png">
  </li>
  <li>Install the shuttle onto the M3x20 screw. Then push the shuttle / screw assembly through the housing a couple times.<br>
      The idea behind this is a push fit of the screw into the plastic housing, it will help it not rotate while printing.<br>
    <img width=200 src="https://github.com/joseph-greiner/tridex_mods/blob/main/hardware_z_adjuster/images/assy_3.png">
  </li>
  <li>The shuttle should move back and forth when turning the screw, but the head of the screw should stay seated on the housing.</li>
  <li>Add the ramp to the assembly then install onto the T1 carriage using the M3x12 in the hole that the Tap switch would mount into.<br>
      The mounting screw should be secure but not tight enough to bind the adjuster.<br>
    <img width=200 src="https://github.com/joseph-greiner/tridex_mods/blob/main/hardware_z_adjuster/images/assy_4.png">
  </li>
  
</ul>

## Images:
<img width=200 src="https://github.com/joseph-greiner/tridex_mods/blob/main/hardware_z_adjuster/images/z_adjust_cad_0.png"><img width=200 src="https://github.com/joseph-greiner/tridex_mods/blob/main/hardware_z_adjuster/images/z_adjust_cad_1.png">
<img width=200 src="https://github.com/joseph-greiner/tridex_mods/blob/main/hardware_z_adjuster/images/z_adjust_stl.png">
<img width=200 src="https://github.com/joseph-greiner/tridex_mods/blob/main/hardware_z_adjuster/images/z_adjust_installed_0.jpg">
<img width=200 src="https://github.com/joseph-greiner/tridex_mods/blob/main/hardware_z_adjuster/images/z_adjust_installed_1.jpg">
