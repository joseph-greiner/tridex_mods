# Printer Configuration
 These are my current configuration and macros for stock Klipper based IDEX machines. When combined with my slicer configuration, these macros allow full printing capabilities with your printer.

## Printing modes:
 Single tool prints (T0 or T1)<br>
 Dual material or dual color printing with both tool heads.<br>
 Copy and Mirror mode printing with any material selected in the slicer.

## Multiple tool head change modes:
 Swap - quickest tool change mode, both tool heads move at the same time. (Ported from Vcore IDEX macros by Helge Keck)<br>
 Classic - original Tridex tool change, one tool head moves at a time.<br>
 Ooze Prevention - if nozzles are cooled down when not actively printing, keeps the tool head in the parking area until printing temperatures is reached

## Tool head offsets adjustable without restarting Klipper
 Macros are available that allow adjusting the tool head offsets during a print (X, Y, and Z supported).<br>
 Macros automatically save the new offsets so they will be kept after Klipper restarts.

## Primary, Copy, and Mirror modes fully supported
## Support for Inductive, Klicky, and Double Tap bed probing with T0
## Support for individual tool head LED activation / colors / effects.

All config files are fully commented and helps walk you through what needs changed and what does not need changed. If you set your board pins, end stops and probe properly. The macros just work.

## Update for January 1, 2024:
Bugfix - corrected T1 offset adjustment macros. fixed z offset compounding error. Offsets now correctly update when T1 is active.

## Update for December 9, 2023:
Bugfix - preferred_tool_change was not loaded at klipper startup, corrected this.<br>
Feature - added a macro to view the current offsets for T1, it will print them to the console.

## Update for December 4, 2023:
Offsets save and load automatically to idex_variables.cfg<br>
Removed and re-organized variables from IDEX_mode.cfg<br>
Removed un-necessary tool changes from the print_start macro, especially if only using T1 in a print.<br>
added T1 Z offset macros.
