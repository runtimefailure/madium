---
description: Compresses data using the LZ4 algorithm.
icon: code-simple
---

# lz4compress



## Syntax

```lua
lz4compress(data: string) -> string
```

## Parameters

| Parameter | Type     | Description          |
| --------- | -------- | -------------------- |
| `data`    | `string` | The data to compress |

## Returns

| Type     | Description             |
| -------- | ----------------------- |
| `string` | The LZ4 compressed data |

## Description

`lz4compress` compresses a string using the LZ4 compression algorithm. LZ4 is optimized for speed over compression ratio, making it ideal for real-time applications.

## Example

```lua
local data = string.rep("Hello, World! ", 1000)
print("Original size:", #data) -- 14000

local compressed = lz4compress(data)
print("Compressed size:", #compressed) -- Much smaller

local decompressed = lz4decompress(compressed, #data)
print(data == decompressed) -- true
```

## Compression Ratio

LZ4 works best with:

* Repetitive data
* Text with patterns
* Structured data

```lua
-- High compression (repetitive data)
local repetitive = string.rep("AAAA", 10000)
local comp1 = lz4compress(repetitive)
print(#comp1 / #repetitive) -- Very small ratio

-- Lower compression (random data)
local random = ""
for i = 1, 1000 do
    random = random .. string.char(math.random(0, 255))
end
local comp2 = lz4compress(random)
print(#comp2 / #random) -- Closer to 1
```

## Related Functions

* [`lz4decompress`](lz4decompress.md) - Decompress LZ4 data
