---
description: Gets the current call stack.
icon: code-simple
---

# getcallstack



## Syntax

```lua
debug.getcallstack(level: number?) -> table
```

## Parameters

| Parameter | Type     | Description                          |
| --------- | -------- | ------------------------------------ |
| `level`   | `number` | (Optional) Starting level, default 1 |

## Returns

| Type    | Description                 |
| ------- | --------------------------- |
| `table` | Array of call stack entries |

## Description

`debug.getcallstack` returns information about the current call stack, including function names and source locations.

## Example

```lua
local function innerFunc()
    local stack = debug.getcallstack()
    for i, entry in ipairs(stack) do
        print(i, entry.name or "anonymous", entry.source)
    end
end

local function outerFunc()
    innerFunc()
end

outerFunc()
```

## Entry Fields

| Field    | Description         |
| -------- | ------------------- |
| `name`   | Function name       |
| `source` | Source file/script  |
| `line`   | Current line number |
| `func`   | The function itself |

## Related Functions

* [`debug.getinfo`](getinfo.md) - Get info for specific level
* [`debug.validlevel`](validlevel.md) - Check if level is valid
