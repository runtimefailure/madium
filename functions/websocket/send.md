---
description: Sends a message through the WebSocket connection.
icon: code-simple
---

# Send



## Syntax

```lua
WebSocket:Send(message: string) -> ()
```

## Parameters

| Parameter | Type     | Description         |
| --------- | -------- | ------------------- |
| `message` | `string` | The message to send |

## Returns

This method does not return a value.

## Description

`WebSocket:Send` transmits a string message to the connected WebSocket server. For structured data, encode it as JSON before sending.

## Example

```lua
local ws = WebSocket.connect("wss://example.com/socket")

-- Send a simple message
ws:Send("Hello, Server!")
```

## JSON Communication

```lua
local HttpService = game:GetService("HttpService")
local ws = WebSocket.connect("wss://api.example.com/ws")

-- Send JSON data
local function sendJSON(data)
    ws:Send(HttpService:JSONEncode(data))
end

sendJSON({
    type = "subscribe",
    channel = "updates"
})

sendJSON({
    type = "message",
    content = "Hello!",
    timestamp = os.time()
})
```

## Multiple Messages

```lua
local ws = WebSocket.connect("wss://echo.websocket.org")

ws.OnMessage:Connect(function(msg)
    print("Echo:", msg)
end)

-- Send multiple messages
ws:Send("First message")
ws:Send("Second message")
ws:Send("Third message")
```

## Notes

* Messages are strings; use JSON for structured data
* Messages are sent asynchronously
* Connection must be open to send

## Related

* [`WebSocket.connect`](connect.md) - Create connection
* [`OnMessage`](onmessage.md) - Receive responses
