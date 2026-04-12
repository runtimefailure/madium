---
description: Retrieves an existing communication channel by its identifier.
icon: code-simple
---

# get\_comm\_channel



## Syntax

```lua
get_comm_channel(id: string) -> Channel
```

## Parameters

| Parameter | Type     | Description            |
| --------- | -------- | ---------------------- |
| `id`      | `string` | The channel identifier |

## Returns

| Type      | Description        |
| --------- | ------------------ |
| `Channel` | The channel object |

## Description

`get_comm_channel` retrieves a communication channel that was created with `create_comm_channel`. This is typically used inside an actor to get a reference to a channel created on the main thread.

## Example

```lua
-- On main thread
local id, channel = create_comm_channel()
channel.Event:Connect(print)

-- Inside actor (via run_on_actor)
run_on_actor(actor, [[\
    local channelId = ...\
    local channel = get_comm_channel(channelId)\
    channel:Fire("Hello from actor!")\
]], id)
```

## Notes

* The channel ID is passed from the main thread to the actor
* Use this inside actors to communicate back to the main thread

## Related Functions

* [`create_comm_channel`](create_comm_channel.md) - Create a channel
* [`run_on_actor`](run_on_actor.md) - Run code on an actor
