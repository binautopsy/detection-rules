# Binautopsy Detection Rules

Curated YARA and Sigma rules for malware families, exploitation
behaviors, and incident artifacts analyzed by Binautopsy Labs.

## Scope

- **What's here:** rules tied to published autopsies and CVE briefs
  on binautopsy.com/research/. Every rule has a reference URL pointing
  to the analysis it came from.
- **What's NOT here:** opportunistic IOC dumps, generic malware-family
  rules pulled from third-party feeds, rules without provenance.

## Quality bar

- Every rule has metadata: author, date, version, reference URL, sample
  hash, license. No anonymous rules.
- Every rule cites the autopsy or brief it came from.
- False-positive notes included where benign software resembles the
  malicious pattern.

## Layout

- `yara/` — YARA rules (validated against `yara` >= 4.5)
- `sigma/` — Sigma rules (validated against `sigma-cli` >= 1.0)

## Reporting false positives

Open a GitHub issue with: rule name, the benign sample/process, the
matching condition, environment context. We respond within 1 business
week.

## Curation policy

External contributions are welcomed via PR but evaluated against the
quality bar above. We curate, we don't aggregate — a rule must come
from defensible analysis, not from speculation.

## License

Apache-2.0. Use freely in commercial and non-commercial detection
tools, including MDR/MSSP integrations. Attribution appreciated.

## About

Binautopsy Labs is a specialist cybersecurity lab focused on
artifact-first investigations. https://binautopsy.com/
