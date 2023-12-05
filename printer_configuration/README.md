# Printer Configuration
 These are my current configuration and macros for Klipper based IDEX machines. When combined with my slicer configuration, these macros allow full printing capabilities with your printer.

## Printing modes:
 Single tool prints (T0 or T1)
 Dual material or dual color printing with both tool heads.
 Copy and Mirror mode printing with any material selected in the slicer.

## Multiple tool head change modes:
 Swap - quickest tool change mode, both tool heads move at the same time. (Ported from Vcore IDEX macros by Helge Keck)
 Classic - original Tridex tool change, one tool head moves at a time.
 Ooze Prevention - if nozzles are cooled down when not actively printing, keeps the tool head in the parking area until printing temperatures is reached

## Tool head offsets adjustable without restarting Klipper
 Macros are available that allow adjusting the tool head offsets during a print (X, Y, and Z supported).
 Macros automatically save the new offsets so they will be kept after Klipper restarts.

## Primary, Copy, and Mirror modes fully supported
## Support for Inductive, Klicky, and Double Tap bed probing with T0
## Support for individual tool head LED activation / colors / effects.

All config files are fully commented and helps walk you through what needs changed and what does not need changed. If you set your board pins, end stops and probe properly. The macros just work.

Update for December 4, 2023:
Offsets save and load automatically to idex_variables.cfg
Removed and re-organized variables from IDEX_mode.cfg
Removed un-necessary tool changes from the print_start macro, especially if only using T1 in a print.
added T1 Z offset macros.
