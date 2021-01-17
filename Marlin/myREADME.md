Important links:
https://www.reddit.com/r/ender3/comments/h8y1ia/marlin_20x_guide_skr_mini_e3_v20_ender_3/
https://www.reddit.com/r/3Dprinting/comments/hx6ab3/bed_leveling_bltouch_inductive_sensor/
https://github.com/bigtreetech/BIGTREETECH-SKR-mini-E3/issues/70
https://github.com/bigtreetech/BIGTREETECH-SKR-mini-E3/issues/39


Steps
1) get a copy of the Marlin files from the latest version
2) get the latest version of the config
3) Before doing any changes start the tracing of the Marlin files
4) Copy the example config files for BTT into Marlin
5) Modify to accept BL - https://www.reddit.com/r/3Dprinting/comments/hx6ab3/bed_leveling_bltouch_inductive_sensor/
First compile
4) Modify according to the steps to have BL working
5) Modify according to the steps in the git hub page (for Eprom)



step 5)
platform
default_envs = STM32F103RC_btt

Main Changes
Configuration.h:
E ENDSTOP_INTERRUPTS_FEATURE
C NOZZLE_TO_PROBE_OFFSET { -44.5, -10, 0.00 }
C PROBING_MARGIN 10
E Z_MIN_PROBE_REPEATABILITY_TEST
E AUTO_BED_LEVELING_BILINEAR
E RESTORE_LEVELING_AFTER_G28
E Z_SAFE_HOMING (If you want to use the probe for homing too)

Configuration_adv.h:
E PROBE_OFFSET_WIZARD
E BABYSTEPPING
C BABYSTEP_MULTIPLICATOR_Z 4
E DOUBLECLICK_FOR_Z_BABYSTEPPING
E BABYSTEP_ZPROBE_OFFSET
E BABYSTEP_ZPROBE_GFX_OVERLAY

BLTOUCH v3.0/v3.1
Configuration.h:
E BLTOUCH
C XY_PROBE_SPEED (100*60)

Configuration_adv.h:
E BLTOUCH_DELAY 500
E BLTOUCH_SET_5V_MODE
