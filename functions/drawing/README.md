---
description: >-
  The Drawing library provides functions for creating and managing visual
  overlays that render on top of the Roblox viewport.
icon: paintbrush
---

# Drawing



## Overview

Drawing objects allow you to create:

* Lines and shapes
* Text labels
* Images
* Custom UI elements

These drawings are rendered directly on the screen and are not part of the Roblox UI system, making them hidden from game scripts.

## Available Functions

| Function                                    | Description                          |
| ------------------------------------------- | ------------------------------------ |
| [`cleardrawcache`](cleardrawcache.md)       | Clear all cached drawing objects     |
| [`getrenderproperty`](getrenderproperty.md) | Get a property from a drawing object |
| [`isrenderobj`](isrenderobj.md)             | Check if a value is a drawing object |
| [`setrenderproperty`](setrenderproperty.md) | Set a property on a drawing object   |

## Creating Drawing Objects

Use `Drawing.new(type)` to create new drawing objects:

```lua
local line = Drawing.new("Line")
line.From = Vector2.new(0, 0)
line.To = Vector2.new(100, 100)
line.Color = Color3.fromRGB(255, 0, 0)
line.Thickness = 2
line.Visible = true
```

## Drawing Types

| Type       | Description                        |
| ---------- | ---------------------------------- |
| `Line`     | A line between two points          |
| `Circle`   | A circle with center and radius    |
| `Square`   | A rectangle                        |
| `Triangle` | A triangle with three vertices     |
| `Text`     | Text label                         |
| `Image`    | An image/texture                   |
| `Quad`     | A quadrilateral with four vertices |

## Common Properties

All drawing objects share these properties:

| Property       | Type      | Description                              |
| -------------- | --------- | ---------------------------------------- |
| `Visible`      | `boolean` | Whether the object is visible            |
| `ZIndex`       | `number`  | Rendering order (higher = on top)        |
| `Transparency` | `number`  | Transparency (0 = opaque, 1 = invisible) |
| `Color`        | `Color3`  | The object's color                       |

## Cleanup

Always remove drawing objects when done:

```lua
local circle = Drawing.new("Circle")
-- ... use the circle ...
circle:Remove()
```
