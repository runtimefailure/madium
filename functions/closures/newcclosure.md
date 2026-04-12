---
description: Wraps a Luau function to appear as a C closure.
icon: code-simple
---

# newcclosure



## Syntax

```
newcclosure(func: function, debugname: string?) -> function
```

## Parameters

| Parameter   | Type       | Description                              |
| ----------- | ---------- | ---------------------------------------- |
| `func`      | `function` | The Luau function to wrap                |
| `debugname` | `string?`  | Optional name for debugging/stack traces |

## Returns

| Type       | Description                                          |
| ---------- | ---------------------------------------------------- |
| `function` | A C closure wrapper that calls the original function |

## Description

`newcclosure` wraps a Luau function so that it appears to be a C closure when inspected. The wrapped function behaves identically but `iscclosure` will return `true` for it.

## Example

```lua
local function myHook(...)
    print("Hooked!")
    return ...
end

-- Check before wrapping
print(iscclosure(myHook)) -- false

-- Wrap it
local wrapped = newcclosure(myHook)

-- Now it appears as a C closure
print(iscclosure(wrapped)) -- true

-- But still works the same
wrapped("test") -- Output: Hooked!
```

## With Debug Name

```lua
local function handler()
    print("Handling request")
end

-- Wrap with a custom debug name
local wrapped = newcclosure(handler, "RequestHandler")

-- The debug name appears in stack traces and debug.info
```

## Notes

* The wrapper has minimal performance overhead
* Errors are modified for hooking purposes
* The optional `debugname` parameter sets the function name for debugging

## Related Functions

* [`newlclosure`](newlclosure.md) - Wrap as Luau closure
* [`iscclosure`](iscclosure.md) - Check if C closure
* [`isnewcclosure`](isnewcclosure.md) - Check if newcclosure
