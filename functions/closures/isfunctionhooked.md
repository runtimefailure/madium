---
description: Checks if a function has been hooked.
icon: code-simple
---

# isfunctionhooked



## Syntax

```lua
isfunctionhooked(func: function) -> boolean
```

## Parameters

| Parameter | Type       | Description           |
| --------- | ---------- | --------------------- |
| `func`    | `function` | The function to check |

## Returns

| Type      | Description                    |
| --------- | ------------------------------ |
| `boolean` | True if the function is hooked |

## Description

`isfunctionhooked` checks whether a function has been replaced using `hookfunction` or similar hooking methods.

## Example

```lua
local function myFunc()
    return "original"
end

print(isfunctionhooked(myFunc)) -- false

hookfunction(myFunc, function()
    return "hooked"
end)

print(isfunctionhooked(myFunc)) -- true
```

## Use Cases

* Checking if a function has already been hooked
* Avoiding double-hooking
* Debugging hook states

## Related Functions

* [`hookfunction`](hookfunction.md) - Hook a function
* [`restorefunction`](restorefunction.md) - Restore original
