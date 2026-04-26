# Contributing

External contributions are welcomed via pull request but evaluated
against the quality bar in [README.md](README.md). We curate, we
don't aggregate.

## Submitting a rule

1. Open a PR adding a single `.yar` or `.yml` file under `yara/` or
   `sigma/`.
2. Include the metadata block specified in
   [docs/attribution.md](docs/attribution.md).
3. Cite the source: a published Binautopsy autopsy/brief, a public
   sample with sha256, or a vendor advisory. Anonymous indicators
   without provenance will be declined.
4. Add false-positive notes if the pattern resembles benign software.

## CI

Every PR runs syntax validation. A failing check blocks merge.

## Reviews

Reviews are performed by the lab's research lead. Response time:
1 business week for community PRs.

## License

By contributing, you agree your contribution is licensed under
Apache-2.0.
