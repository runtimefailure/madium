---
description: Decompresses LZ4 compressed data.
icon: code-simple
---

# lz4decompress



## Syntax

```
lz4decompress(data: string, size: number) -> string
```

## Parameters

| Parameter | Type     | Description                    |
| --------- | -------- | ------------------------------ |
| `data`    | `string` | The LZ4 compressed data        |
| `size`    | `number` | The original uncompressed size |

## Returns

| Type     | Description           |
| -------- | --------------------- |
| `string` | The decompressed data |

## Description

`lz4decompress` decompresses data that was compressed with `lz4compress`. You must provide the original uncompressed size for the decompression to work correctly.

## Example

```lua
local original = "This is the original data that will be compressed!"
local originalSize = #original

-- Compress
local compressed = lz4compress(original)

-- Decompress (need to know original size)
local decompressed = lz4decompress(compressed, originalSize)

print(original == decompressed) -- true
```

## Storing Size with Data

When storing compressed data, you should also store the original size:

```lua
local function compressWithSize(data)
    local compressed = lz4compress(data)
    -- Prepend the size as a 4-byte integer
    local size = #data
    return string.pack("<I4", size) .. compressed
end

local function decompressWithSize(data)
    local size = string.unpack("<I4", data)
    local compressed = data:sub(5)
    return lz4decompress(compressed, size)
end
```

## Notes

* The size parameter must match the original data size exactly
* Providing wrong size may cause errors or corrupted output

## Related Functions

* [`lz4compress`](lz4compress.md) - Compress with LZ4
