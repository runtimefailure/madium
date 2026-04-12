---
description: Checks if a function is a C closure.
icon: code-simple
---

# iscclosure



## Syntax

```
iscclosure(func: function) -> boolean
```

## Parameters

| Parameter | Type       | Description           |
| --------- | ---------- | --------------------- |
| `func`    | `function` | The function to check |

## Returns

| Type      | Description                                              |
| --------- | -------------------------------------------------------- |
| `boolean` | `true` if the function is a C closure, `false` otherwise |

## Description

`iscclosure` returns whether the given function is implemented in C/C++ rather than Luau. C closures include built-in Lua functions, Roblox API methods, and functions wrapped with `newcclosure`.

## Example

```lua
-- Built-in functions are C closures
print(iscclosure(print)) -- true
print(iscclosure(type)) -- true
print(iscclosure(game.GetService)) -- true

-- User-defined functions are Luau closures
local function myFunc()
    return "hello"
end
print(iscclosure(myFunc)) -- false

-- Wrapped functions become C closures
local wrapped = newcclosure(myFunc)
print(iscclosure(wrapped)) -- true
```

## Related Functions

* [`islclosure`](islclosure.md) - Check if a function is a Luau closure
* [`newcclosure`](newcclosure.md) - Wrap a Luau function as a C closure
