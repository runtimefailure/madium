---
description: Restores a hooked function to its original implementation.
icon: code-simple
---

# restorefunction



## Syntax

```lua
restorefunction(func: function) -> void
```

## Parameters

| Parameter | Type       | Description                    |
| --------- | ---------- | ------------------------------ |
| `func`    | `function` | The hooked function to restore |

## Returns

This function does not return a value.

## Description

`restorefunction` removes a hook from a function, restoring it to its original behavior. This is useful for cleanup or when you need to temporarily remove a hook.

## Example

```lua
-- Hook print
local originalPrint = hookfunction(print, function(...)
    originalPrint("[HOOKED]", ...)
end)

print("Test 1") -- Output: [HOOKED] Test 1

-- Restore the original
restorefunction(print)

print("Test 2") -- Output: Test 2 (no prefix)
```

## Notes

* Only works on functions that were hooked by volt
* Has no effect on functions that aren't currently hooked
* The original function reference from `hookfunction` remains valid

## Aliases

* `restorefunc`
