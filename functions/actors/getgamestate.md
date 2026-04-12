---
description: Returns the default game Lua state.
icon: code-simple
---

# getgamestate



## Syntax

```lua
getgamestate() -> LuaStateProxy
```

## Returns

| Type            | Description                               |
| --------------- | ----------------------------------------- |
| `LuaStateProxy` | The LuaStateProxy for the main game state |

## Description

`getgamestate` returns the `LuaStateProxy` for the default game Lua state. This is the main execution environment where most game scripts run.

## Example

```lua
local gameState = getgamestate()
print("Game state ID:", gameState.Id)
print("Is Actor State:", gameState.IsActorState) -- false
```

## Execute Code on Game State

```lua
local gameState = getgamestate()
gameState:Execute([[\
    print("Executed on game state!")\
]])
```

## Compare States

```lua
local gameState = getgamestate()
local currentState = getluastate()

if gameState.Id == currentState.Id then
    print("Running on game state")
else
    print("Running on different state")
end
```

## Related Functions

* [`getluastate`](getluastate.md) - Get LuaStateProxy for a specific actor or script
* [`getactorstates`](getactorstates.md) - Get all active LuaStateProxy objects
* [`getactors`](getactors.md) - Get all Actor instances
