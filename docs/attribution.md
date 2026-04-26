# Attribution: how autopsies become rules

Every rule in this repo traces back to an analysis published at
`binautopsy.com/research/<slug>/`. The link works in both directions:

- The rule's `reference` (YARA) or `references[]` (Sigma) field points
  to the autopsy URL.
- The autopsy at `binautopsy.com/research/<slug>/` includes a Detection
  section pointing back to the rule(s) on this repo.
- The Plan 1 rule-piece template stores `related_autopsy: <slug>` so
  the WP template renders a "Related autopsy" footer.

This bidirectional link is the integrity check: if a rule's metadata
points to an autopsy that doesn't exist, the rule is invalid; if an
autopsy promises detection rules that don't exist on this repo, the
autopsy is incomplete.

## Required YARA metadata

```
meta:
    author = "Binautopsy Labs"
    date = "YYYY-MM-DD"            // first publish date
    version = "1"                   // increment on substantive changes
    reference = "https://binautopsy.com/research/<slug>/"
    hash = "<sha256 of source sample>"
    license = "Apache-2.0"
```

## Required Sigma metadata

```yaml
title: ...
id: <uuid>          # use `uuidgen` to generate
status: experimental
description: ...
author: Binautopsy Labs
date: YYYY-MM-DD
modified: YYYY-MM-DD
references:
    - https://binautopsy.com/research/<slug>/
tags:
    - attack.<technique-id>
    - binautopsy
license: Apache-2.0
```

## Editorial review

Before merging a rule, the operator confirms:

1. The referenced autopsy exists and is published.
2. The hash field matches a real sample (not synthetic).
3. False-positive notes are present if the pattern is broad.
4. The rule actually fires on the source sample (manual check).

CI checks syntax, not these editorial concerns.
