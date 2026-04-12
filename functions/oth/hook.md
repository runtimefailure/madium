---
description: >-
  Secure alternative to hookfunction for C functions. Hooks are executed on
  separate threads.
icon: code-simple
---

# hook



## Syntax

```lua
oth.hook(target: function, hook: function) -> function
```

## Parameters

| Parameter | Type       | Description              |
| --------- | ---------- | ------------------------ |
| `target`  | `function` | The C function to hook   |
| `hook`    | `function` | The replacement function |

## Returns

| Type       | Description                          |
| ---------- | ------------------------------------ |
| `function` | A reference to the original function |

## Description

`oth.hook` replaces the target C function with your hook function. Unlike `hookfunction`, hooks are executed on separate threads, providing better isolation and safety. The function returns a reference to the original, allowing you to call it from within your hook.

## Example

```lua
-- Hook a C function
local originalFunc = oth.hook(someCFunction, function(...)
    print("Hooked call:", ...)
    return originalFunc(...)
end)

-- Call the original
originalFunc("test")
```

## Thread Safety

```lua
local originalPrint = oth.hook(print, function(...)
    -- This runs on a separate thread
    if oth.is_hook_thread() then
        print("[HOOK THREAD]", ...)
    end
    return originalPrint(...)
end)
```

## Notes

* Only works with C functions (not Luau closures)
* Hooks execute on separate threads for better isolation
* Use `oth.is_hook_thread()` to detect hook context
* The returned original can be called to bypass the hook
* Remove hooks with `oth.unhook`

## Related Functions

* [`oth.unhook`](unhook.md) - Remove a hook
* [`oth.get_root_callback`](get_root_callback.md) - Get original function
* [`oth.is_hook_thread`](is_hook_thread.md) - Check hook thread context
