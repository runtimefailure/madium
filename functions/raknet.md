---
description: >-
  Here you can see a description and use of the functions related to our Raknet
  library.
icon: cloud
---

# Raknet



{% hint style="warning" %}
Interacting with Raknet is unsafe. It can cause disconnects, broken game behavior, or account termination. Only use this library if you understand the risks and know exactly what you are doing.
{% endhint %}

### RakNetPacket Object

The `RakNetPacket` object is passed to send hooks. Use it to inspect, modify, or block outgoing packets.

| **Property**    | **Type** | **Description**                          |
| --------------- | -------- | ---------------------------------------- |
| AsBuffer        | `buffer` | The packet payload as a buffer.          |
| AsString        | `string` | The packet payload as a string.          |
| AsArray         | `table`  | The packet payload as an array of bytes. |
| Priority        | `number` | The RakNet send priority.                |
| Reliability     | `number` | The RakNet reliability mode.             |
| OrderingChannel | `number` | The channel used for ordered traffic.    |
| Size            | `number` | The payload size in bytes.               |

***

#### Add Send Hook

```lua
<void> raknet.add_send_hook(<function> hook)
```

* Registers `hook` before a packet is sent.
* Use the hook to inspect, modify, or block the `RakNetPacket`.

{% code title="Example" %}
```lua
local function log_packet(packet)
    print("outgoing packet | size:", packet.Size, "priority:", packet.Priority)
end
raknet.add_send_hook(log_packet)
```
{% endcode %}

***

#### Remove Send Hook

```lua
<void> raknet.remove_send_hook(<function> hook)
```

* Removes a hook registered with `raknet.add_send_hook`.

***

#### Send

```lua
<void> raknet.send(<buffer | string | table> data, <number> priority, <number> reliability, <number> ordering_channel)
```

* Sends a packet manually.
* `data` accepts a buffer, string, or array of bytes.

{% code title="Example" %}
```lua
local payload = { 0x01, 0x02, 0x03, 0x04 }
raknet.send(payload, 0, 0, 0)
```
{% endcode %}

***

### RakNetPacket Methods

#### Set Data

```lua
<void> RakNetPacket:SetData(<buffer | string | table> data)
```

* Replaces the current packet payload with `data`.

#### Block

```lua
<void> RakNetPacket:Block(<void>)
```

* Prevents the current packet from being sent.

***

{% code title="Block Large Packets" %}
```lua
local function block_large_packets(packet)
    if packet.Size > 512 then
        warn("packet is larger than 512 bytes")
        packet:Block()
    end
end
raknet.add_send_hook(block_large_packets)
```
{% endcode %}

{% code title="Modify Packet Data" %}
```lua
local function modify_packet(packet)
    local bytes = packet.AsArray
    if #bytes > 0 then
        bytes[1] = 0x01 --[[ edit first byte ]]
        packet:SetData(bytes)
    end
end
raknet.add_send_hook(modify_packet)
```
{% endcode %}
