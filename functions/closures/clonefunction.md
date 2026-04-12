---
description: Creates a copy of the given function.
icon: code-simple
---

# clonefunction



## Syntax

```lua
clonefunction(func: function) -> function
```

## Parameters

| Parameter | Type       | Description           |
| --------- | ---------- | --------------------- |
| `func`    | `function` | The function to clone |

## Returns

| Type       | Description                     |
| ---------- | ------------------------------- |
| `function` | A copy of the original function |

## Description

`clonefunction` creates an independent copy of a function. The cloned function behaves identically to the original but is a separate entity. This is particularly useful when you need to keep a reference to the original behavior before hooking.

## Example

```lua
-- Clone a function before hooking it
local originalPrint = clonefunction(print)

-- Now hook the original
hookfunction(print, function(...)
    originalPrint("[HOOKED]", ...)
end)

-- The clone still works as the original
originalPrint("This bypasses the hook")

-- The hooked version adds prefix
print("This goes through the hook") -- Output: [HOOKED] This goes through the hook
```

## Notes

* The cloned function shares the same upvalues as the original
* For C closures, the clone wraps the same underlying C function
* Cloning is useful for preserving original behavior during hooks

## Aliases

* `clonefunc`
