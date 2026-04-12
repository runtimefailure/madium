---
description: Decodes a Base64 encoded string.
icon: code-simple
---

# base64decode



## Syntax

```
base64decode(data: string) -> string
```

## Parameters

| Parameter | Type     | Description               |
| --------- | -------- | ------------------------- |
| `data`    | `string` | The Base64 encoded string |

## Returns

| Type     | Description             |
| -------- | ----------------------- |
| `string` | The decoded binary data |

## Description

`base64decode` converts a Base64 encoded string back to its original binary form.

## Example

```lua
local encoded = "SGVsbG8sIFdvcmxkIQ=="
local decoded = base64decode(encoded)
print(decoded) -- "Hello, World!"
```

## Round-trip Example

```lua
local original = "This is a test message!"

-- Encode then decode
local encoded = base64encode(original)
local decoded = base64decode(encoded)

print(original == decoded) -- true
```

## Use Cases

* **API responses**: Decode Base64 data from web APIs
* **Embedded data**: Extract binary data from encoded strings
* **Deserialization**: Decode stored or transmitted data

## Related Functions

* [`base64encode`](base64encode.md) - Encode to Base64

## Aliases

* `base64_decode`
