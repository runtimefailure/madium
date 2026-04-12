---
description: Gets an upvalue from a function by index.
icon: code-simple
---

# getupvalue



## Syntax

```lua
debug.getupvalue(func: function | number, index: number) -> any
```

## Parameters

| Parameter | Type                   | Description                 |
| --------- | ---------------------- | --------------------------- |
| `func`    | `function` or `number` | The function or stack level |
| `index`   | `number`               | The upvalue index (1-based) |

## Returns

| Type  | Description                        |
| ----- | ---------------------------------- |
| `any` | The upvalue at the specified index |

## Description

`debug.getupvalue` retrieves an upvalue (captured variable from an outer scope) from a function. Upvalues are variables that a closure "closes over" from its enclosing environment.

## Example

```lua
local counter = 0
local prefix = "Count: "

local function increment()
    counter = counter + 1
    return prefix .. counter
end

-- Get the upvalues
print(debug.getupvalue(increment, 1)) -- 0 (counter)
print(debug.getupvalue(increment, 2)) -- "Count: " (prefix)

-- After calling the function
increment()
print(debug.getupvalue(increment, 1)) -- 1 (counter was modified)
```

## Use Cases

* **Inspect closures**: See what variables a function has captured
* **Debugging**: Examine the state of captured variables
* **Modification**: Read before modifying with `setupvalue`

## Related Functions

* [`debug.getupvalues`](getupvalues.md) - Get all upvalues
* [`debug.setupvalue`](setupvalue.md) - Modify an upvalue
