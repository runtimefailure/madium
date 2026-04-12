---
description: Removes a hook created with oth.hook.
icon: code-simple
---

# unhook



## Syntax

```lua
oth.unhook(target: function) -> boolean
```

## Parameters

| Parameter | Type       | Description                   |
| --------- | ---------- | ----------------------------- |
| `target`  | `function` | The hooked function to remove |

## Returns

| Type      | Description                               |
| --------- | ----------------------------------------- |
| `boolean` | True if the hook was successfully removed |

## Description

`oth.unhook` removes a hook from a function that was created with `oth.hook`. The function is restored to its original behavior.

## Example

```lua
-- Hook a function
local originalFunc = oth.hook(someCFunction, function(...)
    print("Hooked:", ...)
    return originalFunc(...)
end)

-- Later, remove the hook
local success = oth.unhook(someCFunction)
if success then
    print("Hook removed successfully")
end
```

## Check Hook Status

```lua
local originalFunc = oth.hook(print, function(...)
    print("[HOOKED]", ...)
end)

-- Remove hook
if oth.unhook(print) then
    print("Hook removed")
else
    print("No hook to remove")
end
```

## Notes

* Only works on functions hooked with `oth.hook`
* Returns `false` if the function wasn't hooked or hook removal failed
* The original function reference from `oth.hook` remains valid after unhooking

## Related Functions

* [`oth.hook`](hook.md) - Create a hook
* [`oth.get_root_callback`](get_root_callback.md) - Get original function
