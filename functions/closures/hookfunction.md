---
description: Replaces a function with a custom implementation.
icon: code-simple
---

# hookfunction



## Syntax

```lua
hookfunction(target: function, hook: function) -> function
```

## Parameters

| Parameter | Type       | Description              |
| --------- | ---------- | ------------------------ |
| `target`  | `function` | The function to hook     |
| `hook`    | `function` | The replacement function |

## Returns

| Type       | Description                          |
| ---------- | ------------------------------------ |
| `function` | A reference to the original function |

## Description

`hookfunction` replaces the target function with your hook function. All calls to the original function will now go through your hook instead. The function returns a reference to the original, allowing you to call it from within your hook.

## Example

```lua
-- Hook the print function
local originalPrint = hookfunction(print, function(...)
    originalPrint("[PREFIX]", ...)
end)

print("Hello") -- Output: [PREFIX] Hello

-- You can still use the original
originalPrint("Direct call") -- Output: Direct call
```

## Advanced Example

```lua
-- Hook a game method
local oldNamecall
oldNamecall = hookfunction(
    getrawmetatable(game).__namecall,
    newcclosure(function(self, ...)
        local method = getnamecallmethod()

        if method == "Kick" then
            return -- Block kick
        end

        return oldNamecall(self, ...)
    end)
)
```

## Notes

* Use `checkcaller` to differentiate between your calls and game calls
* Automatically wrapps Luau hooks in `newcclosure` when hooking C closures
* The returned original can be called to bypass the hook
* Restore the hook with `restorefunction`
