---
description: Runs a script on an actor's state.
icon: code-simple
---

# run\_on\_actor



## Syntax

```lua
run_on_actor(actor: Actor, script: string, ...: any) -> void
```

## Parameters

| Parameter | Type     | Description                    |
| --------- | -------- | ------------------------------ |
| `actor`   | `Actor`  | The actor to run the script on |
| `script`  | `string` | The Lua code to execute        |
| `...`     | `any`    | Arguments passed to the script |

## Returns

This function does not return a value.

## Description

`run_on_actor` executes the provided script string on the specified actor's Luau state. This allows you to run code in parallel on different threads.

## Example

```lua
local actor = Instance.new("Actor")
actor.Parent = workspace

run_on_actor(actor, [[\
    print("Hello from actor!")\
    print("Arguments:", ...)\
]], "arg1", "arg2")
```

## With Communication Channel

```lua
local id, channel = create_comm_channel()
channel.Event:Connect(function(message)
    print("Received:", message)
end)

run_on_actor(Instance.new("Actor"), [[\
    local channelId = ...\
    local channel = get_comm_channel(channelId)\
    channel:Fire("Hello from actor!")\
]], id)
```

## Notes

* The script runs in the actor's isolated environment
* Use communication channels to send data back
* Arguments are passed via varargs (`...`)

## Related Functions

* [`getactors`](getactors.md) - Get all actors
* [`create_comm_channel`](create_comm_channel.md) - Create communication channel
