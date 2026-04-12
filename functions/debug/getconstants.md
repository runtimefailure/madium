---
description: Gets all constants from a function.
icon: code-simple
---

# getconstants



## Syntax

```lua
debug.getconstants(func: function | number) -> table
```

## Parameters

| Parameter | Type                   | Description                 |
| --------- | ---------------------- | --------------------------- |
| `func`    | `function` or `number` | The function or stack level |

## Returns

| Type    | Description                               |
| ------- | ----------------------------------------- |
| `table` | An array of all constants in the function |

## Description

`debug.getconstants` returns a table containing all constant values embedded in a function's bytecode. This is useful for inspecting what literal values a function uses.

## Example

```lua
local function greet(name)
    local greeting = "Hello"
    local punctuation = "!"
    return greeting .. ", " .. name .. punctuation
end

local constants = debug.getconstants(greet)
for i, v in ipairs(constants) do
    print(i, type(v), v)
end
--[[\
Output:\
1  string  Hello\
2  string  !\
3  string  ,\
]]
```

## Inspecting Game Functions

```lua
-- Find what strings a function uses
local function findStrings(func)
    local strings = {}
    for i, const in ipairs(debug.getconstants(func)) do
        if type(const) == "string" then
            table.insert(strings, const)
        end
    end
    return strings
end
```

## Notes

* The table is indexed starting at 1
* Some indices may contain `nil` for unused constant slots
* Only works with Luau closures

## Related Functions

* [`debug.getconstant`](getconstant.md) - Get a single constant
* [`debug.setconstant`](setconstant.md) - Modify a constant
