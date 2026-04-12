---
description: A bindable event that fires when an actor is added and ready.
icon: code-simple
---

# on\_actor\_added



## Syntax

```lua
on_actor_added: BindableEvent
```

## Description

`on_actor_added` is a global BindableEvent that fires whenever a new actor is added to the game and its global state has been set up. This allows you to automatically run code on new actors as they're created.

## Event Arguments

| Argument | Type    | Description                       |
| -------- | ------- | --------------------------------- |
| `actor`  | `Actor` | The actor instance that was added |

## Example

```lua
on_actor_added.Event:Connect(function(actor)
    print("New actor added:", actor:GetFullName())
end)
```

## Auto-Setup Actors

```lua
-- Automatically run setup code on all new actors
on_actor_added.Event:Connect(function(actor)
    run_on_actor(actor, [[\
        -- Setup code for each actor\
        print("Actor initialized!")\
    ]])
end)
```

## With Communication Channel

```lua
local id, channel = create_comm_channel()
channel.Event:Connect(function(actorName)
    print("Actor ready:", actorName)
end)

on_actor_added.Event:Connect(function(actor)
    run_on_actor(actor, [[\
        local channelId = ...\
        local channel = get_comm_channel(channelId)\
        channel:Fire(script:GetFullName())\
    ]], id)
end)
```

## Notes

* Fires only after the actor's global state is fully initialized
* Useful for setting up hooks or injecting code into new actors

## Related Functions

* [`getactors`](getactors.md) - Get all existing actors
* [`run_on_actor`](run_on_actor.md) - Run code on an actor
