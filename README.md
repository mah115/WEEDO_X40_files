# WEEDO_X40
CURA profile for WEEDO_X40 printer.  Last tested on CURA 4.8
Known issues:
	 ~~If extruder 2 starts first, the wrong extruder is selected because CURA inserts a T1 command, but it is overwritten by the startup gcode.~~ Added extruder start gcode to make sure it grabs the right tool.
