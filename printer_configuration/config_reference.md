# This file contains explanations for the variables used in the idex_mode.cfg

# [save_variables]
# This is the location and name of the file used to store variables that can be altered without restarting Klipper.
# The variables stored here are X, Y, and Z offsets as well as the tool change method.
# Tool change methods are SWAP, CLASSIC, and OOZE_PREV. Must be in all CAPS. Default is CLASSIC change.

filename: ~/printer_data/config/idex-variables.cfg

# [gcode_macro DC_VARS]
# Variables for safe homing, set to z_endstop location pin OR safe location when using TAP.
variable_homing_safe_x: 150
variable_homing_safe_y: 150
# This feedrate is in mm per minute.
variable_homing_feedrate: 12000

# Distance from end of axis to park the tool head, needed for x/y offsets, default: 3.
# This value must be greater than the X offset between tool heads in order to avoid move out of range errors.
variable_park_distance: 3

# Copy and mirror mode start location for T0, T1 start will be calculated off these values.
# For copy mode, X for T1 will be the bed width / 2 plus the variable_copy_start_x value.
# For mirror mode, X will be the bed width minus the variable_copy_start_x value.
# Y and Z positions are shared by both tool heads with no change.
# This position is where to start the syncronization between the tool heads.
# I recommend placing it near the ending location for your T0 purge.
variable_copy_start_x: 5
variable_copy_start_y: 5
variable_copy_start_z: 5

# Print cooling fans names from your tool head configurations.
variable_fan0: 'print_cooling_t0'
variable_fan1: 'print_cooling_t1'

## Autopark parameters:
## default autopark: 0:inactive - 1:active.
# autopark = 1 will park the tool head during a tool change.
# 0 will just change to the other tool head without moving the other tool head out of the way.
# you are expected to park the inactive manually or with custom gcode.
variable_autopark: 1
# z_hop is how far you want the z to change during a tool change.
variable_z_hop: 1

# Movement speed after a tool change when restoring the gcode_state.
# This value is in mm per second.
variable_movespeed: 250
# How fast do you want to change the tool heads. The printer max_velocity will override this if you try and move too fast.
# Feedrate is in mm per minute.
variable_feedrate: 20000

# Nozzle Scrub / Purge
# Scrub the Nozzle: 1 = Yes, 0 = No
variable_scrub: 1
# How many times to scrub the nozzle, default 5
variable_scrubs: 5
# How fast to move the toolhead in mm per minute, default 3000
variable_prep_spd_xy: 3000
# Extra purging when scrubbing the nozzle, default: 0
variable_purge_length: 0
# How fast to purge the extruder, value is mm per minute. Default: 150
variable_purge_spd: 150
# How far to retract after purging to prevent oozing, default: 0
variable_purge_ret: 0
# How long to pause and wait for oozing in seconds. Default: 1
variable_ooze_dwell: 1
# What is the minimum viable purging temperature in celsius, default 200.
variable_purge_temp_min: 200

#####################################################################
#   Variables below here are set in idex-variables.cfg
#   Don't bother changing these in IDEX_mode.cfg, they will be overridden
#####################################################################

# How tool changes should be done, valid values are:
# SWAP Moves both tool heads at the same time, quickest tool change option.
#      Works best with the following custom g-code added to Tool Change in your slicer:
#      {if wipe_tower}
#      G0 X{wipe_tower_x} Y{wipe_tower_y} F{travel_speed*60} ;move to wipe tower before toolchange
#      {endif}
# CLASSIC Moves tool heads individually, classic Tridex behavior. This is the default value
# OOZE_PREV During tool change, leaves the tool over the parking area while the nozzle re-heats.

# FOR ALL TOOL CHANGE METHODS THE FULL CAPS ARE REQUIRED.

# Set the preferred_tool_change in the idex-variables.cfg to one of the following values:
# preferred_tool_change = 'SWAP'
# preferred_tool_change = 'CLASSIC'
# preferred_tool_change = 'OOZE_PREV'

# Variables to store the tool head offsets, leave a 0.0
# Set your offsets in idex-variables.cfg
variable_offset_x: 0.0
variable_offset_y: 0.0
variable_offset_z: 0.0
# These variables are for the tool change method, do not edit
# Set your preferred tool change in idex-variables.cfg
variable_swap_toolheads: 0
variable_immediate_move: 1
# Copy and mirrror mode T1 temperatures - do not edit, these are sent over by the slicer.
# They will be used during a print start.
variable_t0_copy_mirror_temp_start: 0
variable_t1_copy_mirror_temp_start: 0
variable_t0_copy_mirror_temp_print: 0
variable_t1_copy_mirror_temp_print: 0