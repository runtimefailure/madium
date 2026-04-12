---
description: Gets a property value from a drawing object.
icon: code-simple
---

# getrenderproperty



## Syntax

```lua
getrenderproperty(drawing: Drawing, property: string) -> any
```

## Parameters

| Parameter  | Type      | Description        |
| ---------- | --------- | ------------------ |
| `drawing`  | `Drawing` | The drawing object |
| `property` | `string`  | The property name  |

## Returns

| Type  | Description               |
| ----- | ------------------------- |
| `any` | The value of the property |

## Description

`getrenderproperty` retrieves the current value of a property on a drawing object. This is an alternative to directly accessing properties.

## Example

```lua
local circle = Drawing.new("Circle")
circle.Position = Vector2.new(500, 500)
circle.Radius = 100
circle.Color = Color3.fromRGB(255, 0, 0)
circle.Visible = true

-- Get properties using getrenderproperty
local pos = getrenderproperty(circle, "Position")
local radius = getrenderproperty(circle, "Radius")
local color = getrenderproperty(circle, "Color")

print(pos)    -- 500, 500
print(radius) -- 100
print(color)  -- 1, 0, 0
```

## Properties by Type

### Circle

* `Position` (Vector2)
* `Radius` (number)
* `Filled` (boolean)
* `Thickness` (number)

### Line

* `From` (Vector2)
* `To` (Vector2)
* `Thickness` (number)

### Text

* `Position` (Vector2)
* `Text` (string)
* `Size` (number)
* `Font` (Drawing.Fonts)
* `Center` (boolean)
* `Outline` (boolean)

## Related Functions

* [`setrenderproperty`](setrenderproperty.md) - Set a property
* [`isrenderobj`](isrenderobj.md) - Check if value is a drawing
