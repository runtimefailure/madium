---
description: Sets a property value on a drawing object.
icon: code-simple
---

# setrenderproperty



## Syntax

```lua
setrenderproperty(drawing: Drawing, property: string, value: any) -> void
```

## Parameters

| Parameter  | Type      | Description        |
| ---------- | --------- | ------------------ |
| `drawing`  | `Drawing` | The drawing object |
| `property` | `string`  | The property name  |
| `value`    | `any`     | The new value      |

## Returns

This function does not return a value.

## Description

`setrenderproperty` sets the value of a property on a drawing object. This is an alternative to directly assigning properties.

## Example

```lua
local text = Drawing.new("Text")

-- Set properties using setrenderproperty
setrenderproperty(text, "Position", Vector2.new(100, 100))
setrenderproperty(text, "Text", "Hello, World!")
setrenderproperty(text, "Size", 24)
setrenderproperty(text, "Color", Color3.fromRGB(255, 255, 255))
setrenderproperty(text, "Outline", true)
setrenderproperty(text, "Visible", true)
```

## Batch Updates

```lua
local function updateDrawing(drawing, properties)
    for property, value in pairs(properties) do
        setrenderproperty(drawing, property, value)
    end
end

local circle = Drawing.new("Circle")
updateDrawing(circle, {
    Position = Vector2.new(400, 300),
    Radius = 50,
    Color = Color3.fromRGB(0, 255, 0),
    Filled = true,
    Visible = true
})
```

## Related Functions

* [`getrenderproperty`](getrenderproperty.md) - Get a property
* [`isrenderobj`](isrenderobj.md) - Check if value is a drawing
