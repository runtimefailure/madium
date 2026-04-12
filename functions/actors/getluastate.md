---
description: Returns the LuaStateProxy for a given Actor or loaded script.
icon: code-simple
---

# getluastate



## Syntax

```lua
getluastate(actor_or_script: (Actor | BaseScript)?) -> LuaStateProxy
```

## Parameters

| Parameter         | Type    | Description   |
| ----------------- | ------- | ------------- |
| `actor_or_script` | \`Actor | BaseScript?\` |

## Returns

| Type            | Description                                                       |
| --------------- | ----------------------------------------------------------------- |
| `LuaStateProxy` | The LuaStateProxy for the given Actor or script, or current state |

## Description

`getluastate` returns the `LuaStateProxy` object for a specific Actor or loaded script. If no argument is provided, it returns the `LuaStateProxy` for the current Lua state.

## Example

```lua
-- Get current state
local currentState = getluastate()
print("Current state ID:", currentState.Id)

-- Get state for an actor
local actor = Instance.new("Actor")
actor.Parent = workspace
local actorState = getluastate(actor)
print("Actor state ID:", actorState.Id, "Is Actor:", actorState.IsActorState)
```

## Get State for Script

```lua
-- Get state for a specific script
local script = workspace.SomeScript
local scriptState = getluastate(script)
print("Script state ID:", scriptState.Id)
```

## Access State Properties

```lua
local state = getluastate()
print("State ID:", state.Id)
print("Is Actor State:", state.IsActorState)

-- Get all actors for this state
local actors = state:GetActors()
print("Actors in state:", #actors)
```

## Related Functions

* [`getactorstates`](getactorstates.md) - Get all active LuaStateProxy objects
* [`getgamestate`](getgamestate.md) - Get the default game Lua state
* [`getactors`](getactors.md) - Get all Actor instances
