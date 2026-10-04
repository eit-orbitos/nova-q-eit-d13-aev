# nova-q-eit-d13-aev

**EIT 13D - Autonomous Evolutionary Vector (AEV): Candidate Model for NOVA Q / EIT**

**Author:** Toni Mladenovski
**Brand:** EIT Networks
**Project:** NOVA Q / EIT
**Project origin date:** 18 April 2026
**Source artifact ID:** `EIT_13D_AUTONOMOUS_EVOLUTIONARY_VECTOR_V0.1`
**Release stage:** v0.1.0-rc1 (release candidate, pending independent verification)
**License:** CC BY 4.0

## What this is

A candidate software model that defines the Autonomous Evolutionary Vector (AEV) as a normalized, model-internal transformation-rate candidate, written as `nu_AEV*` (`nu_AEV_star` in code).

Inside the model, the candidate is computed as:

```
nu_AEV* = N_novel * C_coh * V_valid / (delta_t * (1 + R_red))
```

where `N_novel`, `C_coh`, `V_valid` and `R_red` lie in [0, 1] and `delta_t` is strictly positive. The unit is `NORMALIZED_MODEL_INTERNAL_RATE`. Coherence (`C_coh`) and validation (`V_valid`) are separate inputs, and neither implies the other.

The word "frequency" in `aev_frequency.py` and in the code name is a model term. It is not a physical frequency.

## Status boundaries

```text
D13_STATUS                = EXTENSION_CANDIDATE
D_INT_CONTRIBUTION        = UNRESOLVED
PROMOTION_STATUS          = NOT_YET_PROMOTED
PHYSICAL_HZ_CLAIM         = PROHIBITED
AI_CONSCIOUSNESS_CLAIM    = NOT_ESTABLISHED
PHYSICAL_DIMENSION_CLAIM  = NOT_ESTABLISHED
SCIENTIFIC_TRUTH          = NOT_ESTABLISHED
```

## Non-claims

This artifact does not establish:

- a physical frequency (Hz) of any kind
- AI consciousness
- scientific truth
- a promoted or physical 13th dimension

Passing the internal validation gates does not mean something is true. Hash identity does not establish scientific truth or authorial priority.

## Repository contents

Twelve source files (flat, no subfolders):

| # | File |
|---|---|
| 01 | `d13_semantic_contract.py` |
| 02 | `information_fluid_state.py` |
| 03 | `novelty_operator.py` |
| 04 | `validation_operator.py` |
| 05 | `autonomy_gate.py` |
| 06 | `provenance_graph.py` |
| 07 | `falsification_gate.py` |
| 08 | `aev_frequency.py` |
| 09 | `counterexample_families.py` |
| 10 | `audit.py` |
| 11 | `manifest.py` |
| 12 | `test_d13_full.py` |

Metadata and provenance: `README.md`, `LICENSE`, `CITATION.cff`, `.zenodo.json`, `.gitignore`, and `D13_DELIVERY_RECEIPT.md` (per-file SHA-256 table and delivery record).

The twelve source files are the frozen candidate. They must not be edited, renamed or regenerated. Per-file SHA-256 values are in `D13_DELIVERY_RECEIPT.md`.

## How to run the tests

The source files use relative imports, so they must be run as a package. They do not run directly from the repository root.

1. Make a new empty folder and copy only the 12 `.py` files into a subfolder named `d13pkg`.
2. Do not add an `__init__.py` or any other `.py` file. `audit.py` scans every `.py` file in its folder and will fail on extra files.
3. From the folder that contains `d13pkg`, run:

```
python3 -B -m d13pkg.test_d13_full
```

The expected result is `20/20 PASS`. This was checked with Python 3.13; the sources import only the Python standard library.

## Verification status

- The delivery receipt records a prior run in a single sandbox (audit 28/28, full suite 20/20, two rebuilds byte-identical). That is not an independent-environment reproduction.
- Independent verification of the tagged release candidate is pending.
- Zenodo publication is planned only after a final release is verified. This repository does not yet have a DOI.

## How to cite

See `CITATION.cff`. GitHub shows a "Cite this repository" button when that file is present.

## License

Creative Commons Attribution 4.0 International (CC BY 4.0).
https://creativecommons.org/licenses/by/4.0/

Copyright (c) 2026 Toni Mladenovski. EIT Networks is the project brand and does not imply company ownership of the rights.

