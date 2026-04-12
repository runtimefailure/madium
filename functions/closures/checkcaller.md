---
description: Returns whether the current function was called by volt.
icon: code-simple
---

# checkcaller



## Syntax

```lua
checkcaller() -> boolean
```

## Returns

| Type      | Description                                          |
| --------- | ---------------------------------------------------- |
| `boolean` | `true` if called from volt thread, `false` otherwise |

## Description

`checkcaller` returns a boolean indicating whether the current function was invoked from volt's own thread. This is useful for differentiating between your own calls and those made by the game.

When you hook a game function, both your code and the game will trigger it. Use `checkcaller` to determine whether to run custom logic or pass through to the original.

## Example

```lua
local old
old = hookfunction(game.HttpGet, function(self, url, ...)
    if checkcaller() then
        -- Call is from our script, allow it
        return old(self, url, ...)
    end

    -- Call is from the game, we can block or modify it
    print("Game tried to fetch:", url)
    return old(self, url, ...)
end)

-- This will pass checkcaller() because we're calling it
local result = game:HttpGet("https://example.com")
```
