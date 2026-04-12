---
description: Gets a constant from a function at the specified index.
icon: code-simple
---

# getconstant



## Syntax

```lua
debug.getconstant(func: function | number, index: number) -> any
```

## Parameters

| Parameter | Type                   | Description                  |
| --------- | ---------------------- | ---------------------------- |
| `func`    | `function` or `number` | The function or stack level  |
| `index`   | `number`               | The constant index (1-based) |

## Returns

| Type  | Description                               |
| ----- | ----------------------------------------- |
| `any` | The constant value at the specified index |

## Description

`debug.getconstant` retrieves a constant value from a function's bytecode. Constants are literal values like strings, numbers, and booleans that are embedded in the compiled function.

## Example

```lua
local function example()
    local x = "hello"
    local y = 42
    print(x, y)
end

-- Get constants from the function
print(debug.getconstant(example, 1)) -- "hello"
print(debug.getconstant(example, 2)) -- 42
print(debug.getconstant(example, 3)) -- "print" (function name)
```

## Using Stack Level

You can also pass a stack level instead of a function:

```lua
local function inner()
    -- Get constant from the calling function (level 2)
    print(debug.getconstant(2, 1))
end

local function outer()
    local msg = "from outer"
    inner()
end

outer() -- Prints a constant from outer
```

## Notes

* Index is 1-based
* Not all indices may have constants (some may be nil)
* Only works with Luau closures

## Related Functions

* [`debug.getconstants`](getconstants.md) - Get all constants
* [`debug.setconstant`](setconstant.md) - Modify a constant
