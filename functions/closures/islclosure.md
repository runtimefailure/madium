---
description: Checks if a function is a Luau closure.
icon: code-simple
---

# islclosure



## Syntax

```
islclosure(func: function) -> boolean
```

## Parameters

| Parameter | Type       | Description           |
| --------- | ---------- | --------------------- |
| `func`    | `function` | The function to check |

## Returns

| Type      | Description                                                 |
| --------- | ----------------------------------------------------------- |
| `boolean` | `true` if the function is a Luau closure, `false` otherwise |

## Description

`islclosure` returns whether the given function is written in Luau rather than C/C++. Luau closures include user-defined functions and script functions.

## Example

```lua
-- User-defined functions are Luau closures
local function myFunc()
    return "hello"
end
print(islclosure(myFunc)) -- true

-- Built-in functions are NOT Luau closures
print(islclosure(print)) -- false
print(islclosure(type)) -- false

-- Wrapped functions are NOT Luau closures
local wrapped = newcclosure(myFunc)
print(islclosure(wrapped)) -- false
```

## Relationship with iscclosure

`islclosure` is the logical opposite of `iscclosure`:

```lua
local function test() end

print(islclosure(test)) -- true
print(iscclosure(test)) -- false

print(islclosure(test) == not iscclosure(test)) -- true
```

## Related Functions

* [`iscclosure`](iscclosure.md) - Check if a function is a C closure
* [`newcclosure`](newcclosure.md) - Convert a Luau closure to a C closure
