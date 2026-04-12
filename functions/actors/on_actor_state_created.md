---
description: >-
  Event fired when an Actor Lua state is created, before any scripts are
  executed.
icon: code-simple
---

# on\_actor\_state\_created



## Syntax

```lua
on_actor_state_created: BindableEvent
```

## Description

`on_actor_state_created` is a global BindableEvent that fires when a new Actor Lua state is created, before any scripts are executed on that state. This allows you to set up hooks or inject code into new actor states as they're created.

## Event Arguments

| Argument | Type    | Description                                |
| -------- | ------- | ------------------------------------------ |
| `actor`  | `Actor` | The Actor instance whose state was created |

## Example

```lua
on_actor_state_created.Event:Connect(function(actor)
    print("New actor state created:", actor:GetFullName())

    -- Get the state for this actor
    local state = getluastate(actor)
    print("State ID:", state.Id)
end)
```

## Setup Hooks on New States

```lua
on_actor_state_created.Event:Connect(function(actor)
    local state = getluastate(actor)

    -- Execute setup code on the new state
    state:Execute([[\
        -- This runs before any scripts execute on the actor\
        print("Actor state initialized!")\
    ]])
end)
```

## With Communication Channel

```lua
local id, channel = create_comm_channel()
channel.Event:Connect(function(actorName)
    print("Actor state ready:", actorName)
end)

on_actor_state_created.Event:Connect(function(actor)
    local state = getluastate(actor)
    state:Execute([[\
        local channelId = ...\
        local channel = get_comm_channel(channelId)\
        channel:Fire(script:GetFullName())\
    ]], id)
end)
```

## Notes

* Fires before any scripts execute on the actor state
* Useful for setting up hooks or injecting code early
* The state is fully initialized but empty when this fires

## Related Functions

* [`getluastate`](getluastate.md) - Get LuaStateProxy for an actor
* [`on_actor_added`](on_actor_added.md) - Event fired when actor is ready (after scripts load)
* [`getactorstates`](getactorstates.md) - Get all active LuaStateProxy objects
