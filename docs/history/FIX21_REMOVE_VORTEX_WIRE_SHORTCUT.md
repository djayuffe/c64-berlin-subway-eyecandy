# fix21 remove vortex/wire and shorten scenes

Changes:
- Removed vortex from the active part list.
- Removed neon-wire from the active part list.
- Set NUM_PARTS from 28 to 26.
- Removed vx_init/vx_update from InitTbl/UpdateTbl.
- Removed nw_init/nw_update from InitTbl/UpdateTbl.
- Removed the old vortex zone and the neon-wire wrapper zone.
- Kept the full3d cube renderer and wire_cube binary assets because cv_update still uses them.
- Rebuilt title-card tables to 26 entries.
- Shortened every part timer by scaling the old values and clamping to a faster show rhythm.
- Reduced transition card time from 110 to 65 frames.
- Kept clean lowercase !scr text.

Build:
cd mega/src
acme -f cbm -o ../build/subway.prg subway.s
x64sc -autostartprgmode 1 -autostart ../build/subway.prg
