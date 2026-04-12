---
description: Signal that fires when the WebSocket connection is closed.
icon: code-simple
---

# OnClose



## Syntax

```lua
WebSocket.OnClose:Connect(callback: () -> ()) -> Connection
```

## Callback Parameters

This callback receives no parameters.

## Returns

| Type         | Description                           |
| ------------ | ------------------------------------- |
| `Connection` | A connection that can be disconnected |

## Description

`OnClose` is a signal that fires when the WebSocket connection is terminated, either by calling `Close()` or when the server disconnects.

## Example

```lua
local ws = WebSocket.connect("wss://example.com/socket")

ws.OnClose:Connect(function()
    print("Connection closed")
end)

-- Later...
ws:Close()
-- Output: Connection closed
```

## Reconnection Pattern

```lua
local function createConnection()
    local ws = WebSocket.connect("wss://example.com/socket")

    ws.OnClose:Connect(function()
        print("Disconnected, reconnecting in 5 seconds...")
        task.wait(5)
        createConnection()
    end)

    ws.OnMessage:Connect(function(msg)
        print("Message:", msg)
    end)

    return ws
end

local connection = createConnection()
```

## Cleanup on Close

```lua
local ws = WebSocket.connect("wss://example.com/socket")
local isConnected = true

ws.OnClose:Connect(function()
    isConnected = false
    print("Cleaning up...")
    -- Perform cleanup tasks
end)

-- Check connection state before sending
if isConnected then
    ws:Send("Hello!")
end
```

## Related

* [`WebSocket.connect`](connect.md) - Create connection
* [`WebSocket:Close`](close.md) - Close connection
* [`OnMessage`](onmessage.md) - Message event
