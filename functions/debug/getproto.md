---
description: Gets a proto (nested function) from a function.
icon: code-simple
---

# getproto



## Syntax

```lua
debug.getproto(func: function | number, index: number, activated?: boolean) -> function | table
```

## Parameters

| Parameter   | Type                   | Description                              |
| ----------- | ---------------------- | ---------------------------------------- |
| `func`      | `function` or `number` | The function or stack level              |
| `index`     | `number`               | The proto index (1-based)                |
| `activated` | `boolean?`             | If true, returns all activated instances |

## Returns

| Type       | Description                                                    |
| ---------- | -------------------------------------------------------------- |
| `function` | The proto at the specified index (if `activated` is false/nil) |
| `table`    | Array of activated instances (if `activated` is true)          |

## Description

`debug.getproto` retrieves a nested function definition (proto) from within a function. Protos are functions defined inside other functions.

## Example

```lua
local function outer()
    local function inner1()
        print("inner1")
    end

    local function inner2()
        print("inner2")
    end

    inner1()
    inner2()
end

-- Get the first nested function
local proto1 = debug.getproto(outer, 1)
proto1() -- Output: inner1

-- Get the second nested function
local proto2 = debug.getproto(outer, 2)
proto2() -- Output: inner2
```

## Activated Instances

When `activated` is true, returns all instances of the proto that have been created:

```lua
local instances = {}

local function factory()
    local function create()
        return {}
    end
    table.insert(instances, create())
    table.insert(instances, create())
end

factory()

-- Get all activated instances of the inner function
local activated = debug.getproto(factory, 1, true)
print(#activated) -- Number of times the inner function was instantiated
```

## Related Functions

* [`debug.getprotos`](getprotos.md) - Get all protos from a function
