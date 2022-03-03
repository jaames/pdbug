<h1 align="center" dir="auto">
  <img height="340" src="https://raw.githubusercontent.com/jaames/pdbug/master/demo.gif" style="max-width: 100%;"><br>
  pdbug
</h1>
<p align="center" dir="auto">
  <b>"Paint flashing" debug utility for sprite-based Lua Playdate games</b>
</p>

## Overview

Pdbug ("p debug") taps into the Playdate's sprite library to provide a **paint flashing** overlay that highlights sprites when they have been redrawn. By default sprites will only redraw when something has changed, so this can help debug various issues you might run into when building sprite-based scenes and UIs.

This utility relies on [`playdate.debugDraw`](https://sdk.play.date/1.9.0/Inside%20Playdate.html#playdate-debugdraw), and as such it is only available in the Playdate Simulator.

## Quick Start

### Install

All you need to do is <b><a href="https://raw.githubusercontent.com/jaames/pdbug/master/pdbug.lua" download="pdbug.lua" target="_blank">download pd.lua</a></b> from this repo and then drop it into your game's Lua source folder!

### Setup

In your game's `main.lua` file, import the `pdbug.lua` file you just downloaded and then call `pdbug:setEnabled(true)` to enable the debug overlay:

```lua
-- import from wherever you saved the pdbug.lua file
import './pdbug'
-- call this to enable the debugging overlay!
pdbug:setEnabled(true)
```

## Usage and Options

### Methods

#### `pdbug:setEnabled(enabled)`

#### `pdbug:setOverlayColor(r, g, b, a)`

Set the debug overlay color (defaults to `255, 0, 40, 0.75`. `r`, `g` and `b` should be between `0` and `255`, and `a` should be between `0` and `1`.

#### `pdbug:addPaintRect(x, y, w, h)`

Use this if you need to manually add a rectangle to the paint flashing overlay. `x` and `y` should give the position of the rectangle's top-left corner, `w` and `h` should give its width and height.

### Options

#### `pdbug.showFPS`

Boolean indicating whether the FPS counter should be visible when the overlay is enabled. Defaults to true.

#### `pdbug.showPaintFlashing`

Boolean indicating whether paint flashing rectangles should be visible when the overlay is enabled. Defaults to true.

#### `pdbug.paintFlashLineWidth`

The line width to use for paint flashing rectangles, measured in pixels. Defaults to `2`.

#### `pdbug.paintFlashFrameDelay`

How long a paint flashing rectangle should be shown for before it disappears, measured in frames. Defaults to `15`.

----

2022 James Daniel