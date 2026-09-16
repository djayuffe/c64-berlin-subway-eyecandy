# fix22 - text removal, optimization and eyecandy

Base: fix21.

Changes:
- Removed transition subtitle text completely.
- ShowCard now prints one clean centered part name only.
- Removed CardSub0..CardSub25 data and CardSubLo/CardSubHi tables.
- Card transition time reduced from 65 to 45 frames.
- Effect run lengths reduced again for a tighter demo rhythm.
- Added DemoEyeCandy:
  - beat-reactive top/bottom colour rails
  - touches only colour RAM
  - does not overwrite effect chars/pixels
  - driven by musicPulse + beatSin
- Kept vortex and neon-wire removed.
- Kept full3d cube assets because cv_update still uses them.

Static audit:
- 26 InitTbl entries.
- 26 UpdateTbl entries.
- 26 CardName entries.
- 0 CardSub entries.
- No duplicate global labels.
- No empty ACME directives.
- No uppercase in !scr strings.
