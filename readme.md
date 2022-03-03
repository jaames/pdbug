<h1 align="center" dir="auto">
  <img height="340" src="https://raw.githubusercontent.com/jaames/pdbug/master/demo.gif" style="max-width: 100%;"><br>
  pdbug
</h1>
<p align="center" dir="auto">
  <b>Debug overlay utility for Lua-based Playdate games</b>
</p>

## Overview

Pdbug ("p debug") taps into the Playdate's sprite library to provide a **paint flashing** overlay that highlights sprites when they have been redrawn. It can help to find performance issues (less things drawing per frame is better!) and debug various pitfalls you might come across when developing sprite-based games.

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

If `enabled` is true, the overlay will be turned on, otherwise it will be turned off.

#### `pdbug:setOverlayColor(r, g, b, a)`

Set the debug overlay color from red, green, blue and alpha values. 

`r`, `g` and `b` should be between 0 and 255, and `a` should be between 0 and 1. The default color is `255, 0, 40, 0.75`.

#### `pdbug:addPaintRect(x, y, w, h)`

Use this if you ever need to manually add a rectangle to the paint flashing overlay. `x` and `y` should give the position of the rectangle's top-left corner, `w` and `h` should give its width and height.

### Options

#### `pdbug.showFPS`

If set to true, the FPS counter will be visible when the overlay is enabled. Defaults to true.

#### `pdbug.showPaintFlashing`

If set to true, paint flashing rectangles will be visible when the overlay is enabled. Defaults to true.

#### `pdbug.paintFlashLineWidth`

The line width to use for paint flashing rectangles, measured in pixels. Defaults to `2`.

#### `pdbug.paintFlashFrameDelay`

How long a paint flashing rectangle should be shown for before it disappears, measured in frames. Defaults to `15`.

----

2022 James Daniel