---
description: Closes the WebSocket connection.
icon: code-simple
---

# Close



## Syntax

```lua
WebSocket:Close() -> ()
```

## Parameters

This method takes no parameters.

## Returns

This method does not return a value.

## Description

`WebSocket:Close` terminates the WebSocket connection. After closing, the `OnClose` event will fire and no more messages can be sent or received.

## Example

```lua
local ws = WebSocket.connect("wss://example.com/socket")

ws.OnClose:Connect(function()
    print("Connection closed")
end)

-- Use the connection
ws:Send("Hello!")

-- Close after 10 seconds
task.wait(10)
ws:Close()
```

## Cleanup Pattern

```lua
local ws = WebSocket.connect("wss://example.com/socket")

local function cleanup()
    if ws then
        ws:Close()
        ws = nil
    end
end

-- Close on script end or when done
cleanup()
```

## Notes

* Connection cannot be reopened after closing
* `OnClose` event fires after calling Close
* Safe to call multiple times

## Related

* [`WebSocket.connect`](connect.md) - Create connection
* [`OnClose`](onclose.md) - Close event
