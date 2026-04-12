---
description: Removes all cached drawing objects.
icon: code-simple
---

# cleardrawcache



## Syntax

```lua
cleardrawcache() -> void
```

## Returns

This function does not return a value.

## Description

`cleardrawcache` removes all drawing objects that have been created. This is useful for cleanup when you want to clear all visual overlays at once.

## Example

```lua
-- Create several drawings
local drawings = {}
for i = 1, 10 do
    local circle = Drawing.new("Circle")
    circle.Position = Vector2.new(100 * i, 100)
    circle.Radius = 50
    circle.Visible = true
    table.insert(drawings, circle)
end

-- Later, clear everything at once
cleardrawcache()
-- All 10 circles are now removed
```

## Use Cases

* **Script cleanup**: Remove all drawings when a script ends
* **Reset**: Clear all visuals before recreating them
* **Performance**: Free memory from unused drawings

## Notes

* This removes ALL drawings, not just ones you created
* Use with caution in multi-script environments
* Individual drawings can be removed with `:Remove()`
