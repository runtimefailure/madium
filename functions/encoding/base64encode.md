---
description: Encodes data to Base64 format.
icon: code-simple
---

# base64encode



## Syntax

```
base64encode(data: string) -> string
```

## Parameters

| Parameter | Type     | Description               |
| --------- | -------- | ------------------------- |
| `data`    | `string` | The binary data to encode |

## Returns

| Type     | Description               |
| -------- | ------------------------- |
| `string` | The Base64 encoded string |

## Description

`base64encode` converts binary data into a Base64 encoded string that contains only ASCII characters.

## Example

```lua
local data = "Hello, World!"
local encoded = base64encode(data)
print(encoded) -- "SGVsbG8sIFdvcmxkIQ=="
```

## Encoding Binary Data

```lua
-- Encode binary data (like file contents)
local binaryData = "\0\1\2\3\255\254"
local encoded = base64encode(binaryData)
print(encoded) -- Safe ASCII string
```

## Use Cases

* **Data transmission**: Send binary data over text protocols
* **Storage**: Store binary data in JSON or other text formats
* **Obfuscation**: Light obfuscation of string data

## Related Functions

* [`base64decode`](base64decode.md) - Decode from Base64

## Aliases

* `base64_encode`
