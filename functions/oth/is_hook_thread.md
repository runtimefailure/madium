---
description: Returns true if the current thread is a hook thread.
icon: code-simple
---

# is\_hook\_thread



## Syntax

```lua
oth.is_hook_thread() -> boolean
```

## Returns

| Type      | Description                                       |
| --------- | ------------------------------------------------- |
| `boolean` | True if running in a hook thread, false otherwise |

## Description

`oth.is_hook_thread` checks whether the current code is executing within a hook thread created by `oth.hook`. This allows you to detect hook context and behave differently.

## Example

```lua
local originalPrint = oth.hook(print, function(...)
    if oth.is_hook_thread() then
        print("[HOOK THREAD]", ...)
    else
        print("[MAIN THREAD]", ...)
    end
    return originalPrint(...)
end)

print("Test") -- Output: [HOOK THREAD] Test
```

## Conditional Behavior

```lua
local originalFunc = oth.hook(someCFunction, function(...)
    if oth.is_hook_thread() then
        -- Running in hook thread
        print("Hook context detected")
        -- Do hook-specific logic
    end
    return originalFunc(...)
end)
```

## Notes

* Returns `true` only when executing within a hook created by `oth.hook`
* Returns `false` on the main thread or in other contexts
* Useful for implementing hook-specific behavior

## Related Functions

* [`oth.hook`](hook.md) - Create a hook
* [`get_original_thread`](get_original_thread.md) - Get the original thread
