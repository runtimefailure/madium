---
description: Checks if a value is a drawing object.
icon: code-simple
---

# isrenderobj



## Syntax

```lua
isrenderobj(value: any) -> boolean
```

## Parameters

| Parameter | Type  | Description        |
| --------- | ----- | ------------------ |
| `value`   | `any` | The value to check |

## Returns

| Type      | Description                             |
| --------- | --------------------------------------- |
| `boolean` | `true` if the value is a drawing object |

## Description

`isrenderobj` determines whether a given value is a valid drawing object created by `Drawing.new()`.

## Example

```lua
local circle = Drawing.new("Circle")
local normalTable = {}
local number = 123

print(isrenderobj(circle))      -- true
print(isrenderobj(normalTable)) -- false
print(isrenderobj(number))      -- false
print(isrenderobj(nil))         -- false
```

## Use Cases

* **Validation**: Verify that a value is a drawing before manipulating it
* **Cleanup**: Filter drawing objects from a mixed table
* **Debugging**: Identify the type of unknown values

## Example: Safe Removal

```lua
local function safeRemove(obj)
    if isrenderobj(obj) then
        obj:Remove()
        return true
    end
    return false
end
```

## Related Functions

* [`getrenderproperty`](getrenderproperty.md) - Get a drawing property
* [`setrenderproperty`](setrenderproperty.md) - Set a drawing property
