# BERLIN — a trip from the airport to the Golden Heart Hotel

A demo on the **same engine** as the U83R megademo (cloned from megademo.s),
reworked into one continuous narrative: landing at Berlin's airport and riding
the train across the city to the Golden Heart Hotel, scored end to end by
evolving real techno.

## Same engine
- src/subway.s is a clone of megademo.s — identical effect engine, digital-rain
  inter-effect menu, banking, scroller, raster IRQ.  Content + music expanded.

## 28 effects, longer run
- 28 parts (was 24): added vortex, mux edge field, raster boot tunnel and the
  neon wire cube.  Every part also runs ~40% longer — a ~4-minute trip.
- Verified: no CPU jam across the full 28-part loop (2.5B cycles).

## Five evolving real-techno sections (the journey)
- The music flows through 5 sections on each song loop (curSong cycles 2..6):
  departure build -> the journey peak -> through-the-city (melodic) ->
  underground dub breakdown -> arrival rave peak, then loops.
- All on the improved techno engine at ~150 BPM: four-on-the-floor kick, offbeat
  open hats, claps on 2 & 4, 16th hats in the peaks.
- BETTER BASS: rolling resonant-saw — deep SUB drop on beat 1, punchy root/octave
  16th roll, fifth lead-back; V1 ADSR $08/$78 for body; per-bar resonant filter
  "wah".  Sparse dark minor stabs on the offbeats with a release tail (V2 SR $f8).
- Verified dynamic arc: RMS swings from ~1600 (the dub breakdown) to ~2640 (the
  rave peak) — distinct sections, none dead-silent.

## Text — only the trip
- Title:  BERLIN / A TRIP / FROM THE AIRPORT / TO THE GOLDEN HEART HOTEL.
- Every effect card is a station in order: flughafen ber, terminal one two,
  wassmannsdorf, schoenefeld ... alexanderplatz ... kottbusser tor ... and finally
  GOLDEN HEART HOTEL / "you have arrived" (shown as the loop closes).  Subtitles
  are the line/leg ("airport express", "change here", "u2 u5 u8", ...).
- Scroller narrates only the ride — touchdown at flughafen ber, the airport
  express into the tunnel, the city rolling by underground, up the stairs into the
  night — with greet-stops at the key stations, ending at the Golden Heart Hotel.

Build:  acme -f cbm -o build/subway.prg src/subway.s
Run:    x64sc -autostartprgmode 1 -autostart build/subway.prg

## True SID techno implementation pass
- Voice 1 bass now has pulse-width control and true gated rests.
- Voice 2 acid/lead now receives style-specific ADSR, PWM and waveform behaviour.
- Active techno styles use ring-mod, sync and combined waveform colours.
- Filter sweep is now style-dependent, cutoff-saturated, and uses `$d415` low bits for finer movement.
- PWM is style-dependent and clamped away from SID pulse mute edges.

## Fix19 cleanup
- Text and scroller rewritten into tighter true-SID techno lyrics.
- Station cards shortened and corrected.
- Final neon-wire effect no longer uses the old point-placeholder; it now uses the real atlas-driven wireframe renderer.
- Removed stale placeholder wire tables.
