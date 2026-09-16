# Function guide

The source is a single ACME module organized as a small demo engine:

- `MegaMain` initializes memory banking, VIC, the SID player, the scroller, and the first effect.
- `MainLoop` consumes the raster frame flag, reads controls, updates the active part, and runs transitions.
- `InstallIRQ` / `MegaMain_IRQ` install the 50 Hz raster interrupt and tick music/frame timing.
- `InitPart` / `UpdatePart` dispatch the 28 effect parts through the init/update tables.
- `ShowCard`, `PrintCentered`, and `CycleCardColor` render station cards and color animation.
- `GlobalScrollerInit`, `GlobalScroller`, and `ReadKeys` manage the journey text and controls.
- `mr_*` implements matrix rain; `ss_*` the sine starfield; `pl_*` the plasma/raster field; `WireframeGridRender` draws the atlas-backed cube.

The IRQ and main loop use disjoint zero-page locations so the music tick cannot overwrite effect pointers.
