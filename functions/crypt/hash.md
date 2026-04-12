---
description: Generates a hash of the provided data.
icon: code-simple
---

# hash



## Syntax

```
crypt.hash(data: string, algorithm: string?) -> string
```

## Parameters

| Parameter   | Type     | Description                                 |
| ----------- | -------- | ------------------------------------------- |
| `data`      | `string` | The data to hash                            |
| `algorithm` | `string` | (Optional) Hash algorithm, default "SHA256" |

## Returns

| Type     | Description                 |
| -------- | --------------------------- |
| `string` | The hexadecimal hash string |

## Description

`crypt.hash` generates a cryptographic hash of the input data using the specified algorithm.

## Supported Algorithms

* `MD5`
* `SHA1`
* `SHA256` (default)
* `SHA384`
* `SHA512`

## Example

```lua
local data = "Hello, World!"

-- Default SHA256
local hash = crypt.hash(data)
print("SHA256:", hash)

-- Other algorithms
print("MD5:", crypt.hash(data, "MD5"))
print("SHA1:", crypt.hash(data, "SHA1"))
print("SHA512:", crypt.hash(data, "SHA512"))
```

## Use Cases

* Verifying data integrity
* Creating unique identifiers
* Password hashing (prefer `crypt.hmac` for security)

## Related Functions

* [`crypt.hmac`](hmac.md) - HMAC authentication
