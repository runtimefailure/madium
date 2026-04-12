---
description: Returns all active LuaStateProxy objects.
icon: code-simple
---

# getactorstates



## Syntax

```lua
getactorstates() -> {LuaStateProxy}
```

## Returns

| Type              | Description                               |
| ----------------- | ----------------------------------------- |
| `{LuaStateProxy}` | Array of all active LuaStateProxy objects |

## Description

`getactorstates` returns all active `LuaStateProxy` objects in the game. This includes both actor states and the main game state. Each `LuaStateProxy` represents a unique Lua execution environment.

## Example

```lua
local states = getactorstates()
print("Total Lua states:", #states)

for i, state in ipairs(states) do
    print(i, "State ID:", state.Id, "Is Actor:", state.IsActorState)
end
```

## Filter Actor States

```lua
local states = getactorstates()
local actorStates = {}

for _, state in ipairs(states) do
    if state.IsActorState then
        table.insert(actorStates, state)
    end
end

print("Actor states:", #actorStates)
```

## Related Functions

* [`getluastate`](getluastate.md) - Get LuaStateProxy for a specific actor or script
* [`getgamestate`](getgamestate.md) - Get the default game Lua state
* [`getactors`](getactors.md) - Get all Actor instances
