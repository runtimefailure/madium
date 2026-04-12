---
description: Creates a new WebSocket connection to the specified URL.
icon: code-simple
---

# Connect



## Syntax

```
WebSocket.connect(url: string) -> WebSocket
```

## Parameters

| Parameter | Type     | Description                     |
| --------- | -------- | ------------------------------- |
| `url`     | `string` | The WebSocket URL to connect to |

## Returns

| Type        | Description                                |
| ----------- | ------------------------------------------ |
| `WebSocket` | A WebSocket object with methods and events |

## Description

`WebSocket.connect` establishes a persistent connection to a WebSocket server. The URL must use the `ws://` or `wss://` protocol (wss for secure/encrypted connections).

## Example

```lua
-- Connect to a WebSocket server
local ws = WebSocket.connect("wss://echo.websocket.org")

-- Handle incoming messages
ws.OnMessage:Connect(function(message)
    print("Received:", message)
end)

-- Handle connection close
ws.OnClose:Connect(function()
    print("Connection closed")
end)

-- Send a message
ws:Send("Hello, WebSocket!")
```

## Echo Server Example

```lua
local ws = WebSocket.connect("wss://echo.websocket.org")

ws.OnMessage:Connect(function(msg)
    print("Echo:", msg)
end)

-- Send messages that will be echoed back
ws:Send("Test message 1")
ws:Send("Test message 2")
```

## Notes

* WebSocket URLs must use `ws://` or `wss://` protocol
* `wss://` is WebSocket Secure (encrypted)
* Connection is maintained until closed or server disconnects

## Related

* [`WebSocket:Send`](send.md) - Send messages
* [`WebSocket:Close`](close.md) - Close connection
* [`OnMessage`](onmessage.md) - Receive messages
