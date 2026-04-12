---
description: Creates a communication channel for sending messages between actors.
icon: code-simple
---

# create\_comm\_channel



## Syntax

```lua
create_comm_channel(name: string?) -> (string, Channel)
```

## Parameters

| Parameter | Type     | Description                     |
| --------- | -------- | ------------------------------- |
| `name`    | `string` | (Optional) Name for the channel |

## Returns

| Type      | Description            |
| --------- | ---------------------- |
| `string`  | The channel identifier |
| `Channel` | The channel object     |

## Description

`create_comm_channel` creates a new communication channel that can be used to send and receive messages between actors and the main thread.

## Channel Object

| Property/Method | Description                        |
| --------------- | ---------------------------------- |
| `Event`         | Signal to connect for receiving    |
| `Fire(...)`     | Send a message through the channel |

## Example

```lua
local id, channel = create_comm_channel()

-- Listen for messages
channel.Event:Connect(function(message)
    print("Received:", message)
end)

-- Send to an actor
run_on_actor(someActor, [[\
    local channelId = ...\
    local channel = get_comm_channel(channelId)\
    channel:Fire("Hello from actor!")\
]], id)
```

## Bidirectional Communication

```lua
-- Main thread
local id, channel = create_comm_channel()
channel.Event:Connect(function(response)
    print("Actor responded:", response)
end)

-- Actor sends back
run_on_actor(actor, [[\
    local id = ...\
    local channel = get_comm_channel(id)\
    channel:Fire("Message received!")\
]], id)
```

## Related Functions

* [`get_comm_channel`](get_comm_channel.md) - Retrieve a channel
* [`run_on_actor`](run_on_actor.md) - Run code on an actor
