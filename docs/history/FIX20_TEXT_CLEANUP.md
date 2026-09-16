# fix20 text cleanup

Text pass only.

Changed:
- Rewrote title text to a short, clean Berlin / true SID techno identity.
- Rewrote all 28 card subtitles to short station/status words.
- Removed filler prose and joke/pop phrasing from the scroller.
- Kept all !scr text lowercase to avoid C64 charset/gfx mistakes.
- Kept $ff stop markers for station pauses.
- No music engine or wire renderer changes in this pass.

Static audit:
- 28 CardName labels.
- 28 CardSub labels.
- Required title/scroller labels present.
- No duplicate global labels.
- No empty ACME directives.
- No uppercase inside !scr strings.
