# Verification record: v0.1.0-rc1

Scope: byte and test verification of the GitHub tag. No scientific, promotion or
physical assessment is made.

## Subject

- Repository: https://github.com/eit-orbitos/nova-q-eit-d13-aev
- Tag: `v0.1.0-rc1`
- Commit: `66f2de0e39ba871640c645e228078befd2b39e9b`
- Artifact ID: `EIT_13D_AUTONOMOUS_EVOLUTIONARY_VECTOR_V0.1`

## Method

- Fresh shallow clone of the tag only; no earlier chat code used.
- Verifier: Claude (Sonnet 5.5), 2026-10-04.
- Environment: one sandbox, Python 3.13.16. The 12 sources were copied into a
  temporary package folder with no extra `.py` file and run with
  `python3 -B -m <package>.test_d13_full`.

## Results

| Check | Result |
|---|---|
| 12 canonical `.py` files present, exact set | match |
| SHA-256 and size of each of the 12 files vs `D13_DELIVERY_RECEIPT.md` | 12/12 match |
| `test_d13_full.py` | 20/20 PASS |
| `audit.py` | 28/28 PASS, verdict PASS |
| `build_manifest()` run twice | identical output |
| `CONTENT_MANIFEST_SHA256` | match: `bf338d58625aa9c187928013a8bd83fa4b061da1e4deddf1ecb22e849d6176da` |
| `SOURCE_TREE_MANIFEST_SHA256` | match: `b9e3a1eab4dc0b666392241930e04868a5179c28368a94e157ad3f4edfa2cef3` |
| `SOURCE_INVENTORY_SHA256` | match: `8e75f5b3cf01f4911a8b6ae49ee537d57a6bfd403a773ba87333630082b561c6` |
| Entries of the inventory JSON vs the 12 tag files | 12/12 match |

The inventory JSON was supplied by the author. Its hash matched the anchor and
its entries matched the tag files. The recipe is in `SOURCE_INVENTORY_RECIPE.md`.

## Limits

- One verifier, one environment, one run. This is a check by a second party,
  not a multi-environment reproduction.
- The manifest embeds `independent_reexecution: NOT_PERFORMED`. That value is
  part of the hashed content and is unchanged by this record.
- The ZIP hash is not part of this check.

## Retained status

```text
D13_STATUS = EXTENSION_CANDIDATE
D_INT_CONTRIBUTION = UNRESOLVED
PROMOTION_STATUS = NOT_YET_PROMOTED
PHYSICAL_HZ_CLAIM = PROHIBITED
AI_CONSCIOUSNESS_CLAIM = NOT_ESTABLISHED
SCIENTIFIC_TRUTH = NOT_ESTABLISHED
```

Freeze and promotion authority exercised by the verifier: none.
