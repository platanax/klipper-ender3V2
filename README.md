## Configuration for an Ender 3 V2 running Klipper / Mainsail
- Stock extruder
- CR Touch
- Rasberry Pi 4
- Logitech C920 webcam
- Klipper Screen (piTFT50 V2.1)



## Features
* KAMP iuntegration to optimize bed mesh for each print
* SpoolMan helps you to keep track of your filament spools and of your remaining filament weight
* Backup your config files
* Easy filament settings adjustment between your slicer and the prints : override each of your filament's measured calibration parameters in OrcaSlicer and adjust each print seamlessly for your filament

## G-code for OrcaSlicer
### Start G-code for printer
```
;Nozzle diameter =[nozzle_diameter]
;Filament type =[filament_type]
;Filament name = [filament_type]
;Filament weight = [extruded_weight_total]
;M190 S[hot_plate_temp_initial_layer]
;M109 S[nozzle_temperature_initial_layer]
START_PRINT EXTRUDER_TEMP=[nozzle_temperature_initial_layer]  BED_TEMP=[hot_plate_temp_initial_layer] MATERIAL_TYPE=[filament_type]  LAYER_HEIGHT=[layer_height]
```

=======
### Start G-code for filament
```
; filament start gcode
SET_RETRACTION RETRACT_LENGTH=[filament_retraction_length] RETRACT_SPEED=[filament_retraction_speed]
```

## Sources
* Initial conf from : https://github.com/LeeOtts/Ender3v2-Klipper-Configs
* Backup from : https://docs.vorondesign.com/community/howto/EricZimmerman/BackupConfigToGithub.html
* KAMP : https://github.com/kyleisah/Klipper-Adaptive-Meshing-Purging?tab=readme-ov-file
* OBICO with local obico-server
* Spool management : https://github.com/Donkie/Spoolman?tab=readme-ov-file
* Test Speed macros : https://ellis3dp.com/Print-Tuning-Guide/articles/determining_max_speeds_accels.html#usage-of-the-test_speed-macro
* Klipper Shake&Tune : https://github.com/Frix-x/klippain-shaketune
>>>>>>> 8b6b1fabe30b704dbd971361d287998bf9494e27
