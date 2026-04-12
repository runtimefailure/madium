---
description: Gets all upvalues from a function.
icon: code-simple
---

# getupvalues



## Syntax

```lua
debug.getupvalues(func: function | number) -> table
```

## Parameters

| Parameter | Type                   | Description                 |
| --------- | ---------------------- | --------------------------- |
| `func`    | `function` or `number` | The function or stack level |

## Returns

| Type    | Description                               |
| ------- | ----------------------------------------- |
| `table` | A table mapping indices to upvalue values |

## Description

`debug.getupvalues` returns a table containing all upvalues (captured variables) of a function.

## Example

```lua
local a = 1
local b = "hello"
local c = {key = "value"}

local function example()
    print(a, b, c.key)
end

local upvalues = debug.getupvalues(example)
for i, v in pairs(upvalues) do
    print(i, type(v), v)
end
--[[\
Output:\
1  number   1\
2  string   hello\
3  table    table: 0x...\
]]
```

## Practical Use

```lua
-- Find all string upvalues in a function
local function getStringUpvalues(func)
    local strings = {}
    for i, upvalue in pairs(debug.getupvalues(func)) do
        if type(upvalue) == "string" then
            strings[i] = upvalue
        end
    end
    return strings
end
```

## Related Functions

* [`debug.getupvalue`](getupvalue.md) - Get a single upvalue
* [`debug.setupvalue`](setupvalue.md) - Modify an upvalue
