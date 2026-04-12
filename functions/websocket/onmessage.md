---
description: Signal that fires when a message is received from the server.
icon: code-simple
---

# OnMessage



## Syntax

```lua
WebSocket.OnMessage:Connect(callback: (message: string) -> ()) -> Connection
```

## Callback Parameters

| Parameter | Type     | Description          |
| --------- | -------- | -------------------- |
| `message` | `string` | The received message |

## Returns

| Type         | Description                           |
| ------------ | ------------------------------------- |
| `Connection` | A connection that can be disconnected |

## Description

`OnMessage` is a signal that fires whenever the WebSocket server sends a message. Connect a handler function to process incoming messages.

## Example

```lua
local ws = WebSocket.connect("wss://echo.websocket.org")

ws.OnMessage:Connect(function(message)
    print("Received:", message)
end)

ws:Send("Hello!")
-- Output: Received: Hello!
```

## JSON Messages

```lua
local HttpService = game:GetService("HttpService")
local ws = WebSocket.connect("wss://api.example.com/ws")

ws.OnMessage:Connect(function(message)
    local data = HttpService:JSONDecode(message)

    if data.type == "update" then
        print("Update:", data.payload)
    elseif data.type == "error" then
        warn("Error:", data.message)
    end
end)
```

## Message Queue Pattern

```lua
local ws = WebSocket.connect("wss://example.com/socket")
local messageQueue = {}

ws.OnMessage:Connect(function(message)
    table.insert(messageQueue, {
        content = message,
        time = os.time()
    })
end)

-- Process messages elsewhere
local function processQueue()
    for _, msg in ipairs(messageQueue) do
        print(msg.time, msg.content)
    end
    table.clear(messageQueue)
end
```

## Related

* [`WebSocket.connect`](connect.md) - Create connection
* [`WebSocket:Send`](send.md) - Send messages
* [`OnClose`](onclose.md) - Connection close event
