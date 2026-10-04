# SOURCE_INVENTORY_SHA256 recipe

This note records how `SOURCE_INVENTORY_SHA256` is computed for
`EIT_13D_AUTONOMOUS_EVOLUTIONARY_VECTOR_V0.1`. It is a documentation file, not
code, so it does not add a `.py` file to the repository root (`audit.py`
requires exactly 12 `.py` files in its folder).

## Anchor

```
SOURCE_INVENTORY_SHA256 = 8e75f5b3cf01f4911a8b6ae49ee537d57a6bfd403a773ba87333630082b561c6
```

## Recipe (frozen)

```
object              = the JSON object stored in SOURCE_INVENTORY.json
serialization       = canonical JSON
sort_keys           = False   (key order is as stored)
separators          = (",", ":")   (no whitespace)
ensure_ascii        = False
allow_nan           = False
encoding            = UTF-8
final newline       = NONE inside the hashed payload
hash target         = the canonical serialized payload, NOT the file bytes
digest              = SHA-256, lowercase hex
```

`SOURCE_INVENTORY.json` in this repository ends with one newline character for
readability. That newline is not part of the hashed payload. Hashing the file
bytes as-is gives a different value on purpose.

With the current key order, `sort_keys=True` gives the same result. The frozen
recipe still uses `sort_keys=False`.

## Reproduce

Run this in a Python 3 shell from the repository root:

```python
import json, hashlib

with open("SOURCE_INVENTORY.json", encoding="utf-8") as fh:
    obj = json.loads(fh.read())

payload = json.dumps(
    obj, separators=(",", ":"), ensure_ascii=False, allow_nan=False
).encode("utf-8")

print(hashlib.sha256(payload).hexdigest())
```

Expected output:

```
8e75f5b3cf01f4911a8b6ae49ee537d57a6bfd403a773ba87333630082b561c6
```

## What this hash does and does not show

- It identifies the inventory object: artifact ID, the 12 source files with
  their SHA-256 and sizes, the inventory policy, and the source count.
- To check that the repository files match the inventory, also compare each
  entry's `sha256` and `size_bytes` with the actual file.
- A matching hash does not establish scientific truth, promotion, a physical
  frequency, or AI consciousness.
