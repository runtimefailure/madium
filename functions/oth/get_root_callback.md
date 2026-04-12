---
description: Returns the original function, even after multiple hooks.
icon: code-simple
---

# get\_root\_callback



## Syntax

```lua
oth.get_root_callback(target: function) -> function?
```

## Parameters

| Parameter | Type       | Description         |
| --------- | ---------- | ------------------- |
| `target`  | `function` | The hooked function |

## Returns

| Type        | Description                                |
| ----------- | ------------------------------------------ |
| `function?` | The original function, or nil if not found |

## Description

`oth.get_root_callback` returns the original function that was hooked, even if multiple hooks have been applied. This allows you to bypass all hooks and call the true original function.

## Example

```lua
-- Hook a function multiple times
local hook1 = oth.hook(someCFunction, function(...)
    print("Hook 1")
    return hook1(...)
end)

local hook2 = oth.hook(someCFunction, function(...)
    print("Hook 2")
    return hook2(...)
end)

-- Get the original, bypassing all hooks
local original = oth.get_root_callback(someCFunction)
original("test") -- Calls the true original, bypassing both hooks
```

## Bypass All Hooks

```lua
local hookedFunc = oth.hook(print, function(...)
    print("[HOOKED]", ...)
end)

-- Get original to bypass hook
local original = oth.get_root_callback(print)
if original then
    original("Direct call") -- Bypasses the hook
end
```

## Notes

* Returns `nil` if the function was never hooked or is not a C function
* Always returns the true original, regardless of how many hooks exist
* Useful for completely bypassing all hook layers

## Related Functions

* [`oth.hook`](hook.md) - Create a hook
* [`oth.unhook`](unhook.md) - Remove a hook
