---
description: Generates an HMAC (Hash-based Message Authentication Code).
icon: code-simple
---

# hmac



## Syntax

```
crypt.hmac(data: string, key: string, algorithm: string?) -> string
```

## Parameters

| Parameter   | Type     | Description                                 |
| ----------- | -------- | ------------------------------------------- |
| `data`      | `string` | The data to authenticate                    |
| `key`       | `string` | The secret key                              |
| `algorithm` | `string` | (Optional) Hash algorithm, default "SHA256" |

## Returns

| Type     | Description              |
| -------- | ------------------------ |
| `string` | The HMAC as a hex string |

## Description

`crypt.hmac` generates a keyed-hash message authentication code, which provides both data integrity and authentication.

## Supported Algorithms

* `MD5`
* `SHA1`
* `SHA256` (default)
* `SHA384`
* `SHA512`

## Example

```lua
local data = "Important message"
local key = "secret_key"

local mac = crypt.hmac(data, key, "SHA256")
print("HMAC:", mac)
```

## Verification Example

```lua
local function verifyMessage(data, key, expectedHmac)
    local computed = crypt.hmac(data, key)
    return computed == expectedHmac
end

local key = "my_secret"
local message = "Hello"
local signature = crypt.hmac(message, key)

-- Later, verify the message
if verifyMessage(message, key, signature) then
    print("Message is authentic!")
end
```

## Related Functions

* [`crypt.hash`](hash.md) - Simple hashing
