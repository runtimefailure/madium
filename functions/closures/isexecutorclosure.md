---
description: Checks if a function originates from volt.
icon: code-simple
---

# isexecutorclosure



## Syntax

```
isexecutorclosure(func: function) -> boolean
```

## Parameters

| Parameter | Type       | Description           |
| --------- | ---------- | --------------------- |
| `func`    | `function` | The function to check |

## Returns

| Type      | Description                                            |
| --------- | ------------------------------------------------------ |
| `boolean` | `true` if the function is from volt, `false` otherwise |

## Description

`isexecutorclosure` determines whether a function was created by or is part of volt's environment. This includes both volt-provided functions (like `loadstring`, `hookfunction`) and functions defined in your scripts.

## Example

```lua
-- Volt functions return true
print(isexecutorclosure(loadstring)) -- true
print(isexecutorclosure(hookfunction)) -- true

-- Your script functions return true
local function myFunc()
    return "hello"
end
print(isexecutorclosure(myFunc)) -- true

-- Game functions return false
print(isexecutorclosure(print)) -- false
print(isexecutorclosure(game.GetService)) -- false
```

## Related Functions

* [`checkcaller`](checkcaller.md) - Check if the current call is from volt's thread
* [`iscclosure`](iscclosure.md) - Check if a function is a C closure
* [`islclosure`](islclosure.md) - Check if a function is a Luau closure

## Aliases

* `checkclosure`
* `isourclosure`
