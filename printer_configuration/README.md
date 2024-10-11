# Printer Configuration

These are my current configuration and macros for stock Klipper based IDEX machines. When combined with my slicer configuration, these macros allow full printing capabilities with your printer with little to no modifications.

## Printing modes:

Single tool prints (T0 or T1)<br>
Dual material or dual color printing with both tool heads.<br>
Copy and Mirror mode printing with whatever materials are selected in the slicer.<br>

## Multiple tool head change modes:

<b>Swap:</b> Quickest tool change mode, both tool heads move at the same time. (Ported from Vcore IDEX macros by Helge Keck)<br>
<b>Classic:</b> Original Tridex tool change, one tool head moves at a time.<br>
<b>Ooze Prevention</b> If nozzles are cooled down when not actively printing, keeps the tool head in the parking area until printing temperatures are reached<br>
When ooze prevention is checked from within Prusa Slicer, this mode is automatically selected, no changes to your printer configuration needs to be done.<br>

## Tool head offsets adjustable without restarting Klipper

Macros are available that allow adjusting the tool head offsets during a print (X, Y, and Z supported).<br>
Macros automatically save the new offsets so they will be kept after Klipper restarts.

## Primary, Copy, and Mirror modes fully supported

## Support for Inductive, Klicky, and Double Tap bed probing with T0

## Support for individual tool head LED activation / colors / effects.

## Filament runout and rollover support

All config files are fully commented and helps walk you through what needs changed and what does not need changed. If you set your board pins, end stops and probe properly. The macros just work.

# Update for October 10, 2024:
FIXED - Move out of range homing if T1 left active and Y offset was negative. Updated Klicky and IDEX homing overrides.
FIXED - Commented out chamber thermistor by request... No more ADC out of range errors when you don't have one installed.
FIXED - Added config_reference.md file.

# Update for April 23, 2024:

Improved swap tool change macros. Pulled tool head locations from a better place, simplified the math for the tool change.
Updated comments in idex_variables.cfg 

# Update for March 27, 2024:

Improved comments and examples throughout all macro files. <br>
Moved filament sensor definitions and macros to filament_macros.cfg. Makes them more modular and easy to use if desired.<br>
Added places in the print_start for Stealthburner macro calls.<br>
Added support for M601 - Pause at layer from the slicer.<br>
Added some support for M600 with 2 modes:
<ul>
  <li>Default behavior should be similar to other printers. When M600 is called the print pauses and prompts the user to unload, then load new filament. Once the filament is purged to the users satisfaction, they click resume and the print continues.</li>
  <li>Optional behavior, at any time M600 can be called with "M600 CHANGE=1" to initiate a filament rollover during a print. Additionally, there is a variable in the FILAMENT_VARS macro that if set will have M600 always have this behavior.</li>
  <li>NOTE: this is not a full implementation of the M600 macro from Marilin, it triggers on the active extruder when used with the default behavior. If care is used when applying it in the slicer then there should be no issues. If you find any, feedback is always welcome.</li>
</ul>

Added variables in FILAMENT_VARS for length of filament to continue to print after the sensor is triggered. The distance from the extruder to filament sensor is a good start.<br>
Added a timer variable for how often Klipper will check extruded filament since runout switch triggered. Shorter time, more accurate counting, but may block printing movements. 5 seconds has proved reliable in my testing.<br>

# Update for March 17, 2024:

Improved print_start:

  <ul>
    <li> Fewer and smarter tool changes.</li>
    <li> Pre-heat for the print over parking areas to prevent oozing.</li>
    <li> Smarter filament purging, only purges used tool. Purges first tool used in the print last</li>
    <li> If z offset for T1 is set to 0.0, can purge both tool heads at the same time.</li>
    <li> Will not re-home or perform z_tilt adjust if already performed.</li>
    <li> Supports current Klipper adaptive bed mesh.</li>
    <li> Better support for the following printing situations:</li>
    <ul>
        <li> T0 only prints.</li>
        <li> T1 only prints.</li>
        <li> T0 start and T1 prints.</li>
        <li> T1 start and T0 prints.</li>
        <li> Ooze prevention prints, with T0 or T1 as the starting tool head.</li>
        <li> Copy and Mirror mode printing.</li>
    </ul>
    <li> Better print starting if T1 left as the active extruder.</li>
    <li> Better print starting if last print was COPY or MIRROR mode.</li>
  </ul>
  
Improved tool change macros:

  <ul>
    <li>Fixed z_hop for tool change.</li>
    <li>Can now use the T0 and T1 macros if the printer is not homed to change active tool head. Makes filament loading and unloading a little easier.</li>
  </ul>

Improved save_config support:

  <ul>
   <li>Moved hot end PID settings into printer.cfg so when tuning you can save_config and it will not error. (thanks Old Guy Melts Plastic)</li>
  </ul>

Added Filament runout sensor support:

  <ul>
   <li>Loading filament macro added.</li>
   <ul>
      <li>When filament is inserted, will heat the corresponding tool to a default temperature if not heated.</li>
      <li>Otherwise will advance the filament after a configurable delay.</li>
   </ul>
   <li>Filament rollover supported - if one tool head runs out of filament then the other tool will finish the print.</li>
  </ul>

## !!IMPORTANT!! -- New Prusa Slicer Start G-code for PRIMARY mode printing:
    print_start print_mode="PRIMARY" t0_starting_temp={first_layer_temperature[0]} t1_starting_temp={first_layer_temperature[1]} ooze_prev={ooze_prevention} initial_tool={initial_extruder}

# Update for January 1, 2024:

Bugfix - corrected T1 offset adjustment macros. fixed z offset compounding error. Offsets now correctly update when T1 is active.

# Update for December 9, 2023:

Bugfix - preferred_tool_change was not loaded at klipper startup, corrected this.<br>
Feature - added a macro to view the current offsets for T1, it will print them to the console.

# Update for December 4, 2023:

Offsets save and load automatically to idex_variables.cfg<br>
Removed and re-organized variables from IDEX_mode.cfg<br>
Removed un-necessary tool changes from the print_start macro, especially if only using T1 in a print.<br>
added T1 Z offset macros.
