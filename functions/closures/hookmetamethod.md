---
description: Hooks a metamethod on an object's metatable.
icon: code-simple
---

# hookmetamethod



## Syntax

```
hookmetamethod(object: any, metamethod: string, hook: function) -> function
```

## Parameters

| Parameter    | Type       | Description                                         |
| ------------ | ---------- | --------------------------------------------------- |
| `object`     | `any`      | An object with the target metatable                 |
| `metamethod` | `string`   | The metamethod name (e.g., `__index`, `__namecall`) |
| `hook`       | `function` | The replacement function                            |

## Returns

| Type       | Description                            |
| ---------- | -------------------------------------- |
| `function` | A reference to the original metamethod |

## Description

`hookmetamethod` replaces a metamethod in an object's metatable with your custom function. This is commonly used to intercept method calls, property accesses, and other metamethod operations on Roblox instances.

## Example

```lua
-- Hook __namecall to intercept method calls
local oldNamecall
oldNamecall = hookmetamethod(game, "__namecall", newcclosure(function(self, ...)
    local method = getnamecallmethod()

    if method == "GetService" then
        print("GetService called with:", ...)
    end

    return oldNamecall(self, ...)
end))

-- This triggers the hook
local players = game:GetService("Players")
```

## Common Metamethods

| Metamethod   | Triggered By                             |
| ------------ | ---------------------------------------- |
| `__index`    | Property reads (`obj.Property`)          |
| `__newindex` | Property writes (`obj.Property = value`) |
| `__namecall` | Method calls (`obj:Method()`)            |
| `__tostring` | `tostring(obj)`                          |
| `__eq`       | Equality comparison (`obj1 == obj2`)     |

## Notes

* Automatically uses `newcclosure` when hooking metamethods on Roblox objects
* Use `getnamecallmethod` inside `__namecall` hooks to get the method name
* Multiple objects may share the same metatable
* Use `checkcaller` to filter volt vs game calls
