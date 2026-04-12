---
description: Gets all protos (nested functions) from a function.
icon: code-simple
---

# getprotos



## Syntax

```lua
debug.getprotos(func: function | number) -> table
```

## Parameters

| Parameter | Type                   | Description                 |
| --------- | ---------------------- | --------------------------- |
| `func`    | `function` or `number` | The function or stack level |

## Returns

| Type    | Description                            |
| ------- | -------------------------------------- |
| `table` | An array of all protos in the function |

## Description

`debug.getprotos` returns a table containing all nested function definitions within a function.

## Example

```lua
local function container()
    local function a() return 1 end
    local function b() return 2 end
    local function c() return 3 end
    return a() + b() + c()
end

local protos = debug.getprotos(container)
print(#protos) -- 3

for i, proto in ipairs(protos) do
    print(i, proto()) -- Calls each nested function
end
--[[\
Output:\
1  1\
2  2\
3  3\
]]
```

## Use Cases

* **Script analysis**: Find all functions defined within a script
* **Hooking**: Locate specific nested functions to hook
* **Debugging**: Inspect the structure of complex functions

## Related Functions

* [`debug.getproto`](getproto.md) - Get a single proto by index
