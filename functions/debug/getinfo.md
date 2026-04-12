---
description: Gets information about a function or stack level.
icon: code-simple
---

# getinfo



## Syntax

```lua
debug.getinfo(func_or_level: function | number, what: string?) -> table
```

## Parameters

| Parameter       | Type              | Description                    |
| --------------- | ----------------- | ------------------------------ |
| `func_or_level` | `function/number` | Function or stack level        |
| `what`          | `string`          | (Optional) What info to return |

## Returns

| Type    | Description              |
| ------- | ------------------------ |
| `table` | Information about target |

## Description

`debug.getinfo` returns a table with information about a function or the function at a given stack level.

## Info Fields

| Field             | What | Description                  |
| ----------------- | ---- | ---------------------------- |
| `name`            | `n`  | Function name                |
| `source`          | `S`  | Source identifier            |
| `short_src`       | `S`  | Short source name            |
| `what`            | `S`  | "Lua", "C", or "main"        |
| `currentline`     | `l`  | Current line                 |
| `linedefined`     | `S`  | Line where definition starts |
| `lastlinedefined` | `S`  | Line where definition ends   |
| `nups`            | `u`  | Number of upvalues           |
| `nparams`         | `u`  | Number of parameters         |
| `func`            | `f`  | The function itself          |

## Example

```lua
local function myFunc()
    return "hello"
end

local info = debug.getinfo(myFunc)
print("Name:", info.name)
print("Source:", info.short_src)
print("Line defined:", info.linedefined)

-- Get info for current function
local currentInfo = debug.getinfo(1)
print("Current function:", currentInfo.name)
```

## Related Functions

* [`debug.getcallstack`](getcallstack.md) - Get full call stack
* [`debug.validlevel`](validlevel.md) - Check if level is valid
