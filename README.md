# oe-interdisciplinary-k12

[![Validate](https://github.com/openevo-ccs/oe-interdisciplinary-k12/actions/workflows/validate.yml/badge.svg)](https://github.com/openevo-ccs/oe-interdisciplinary-k12/actions/workflows/validate.yml)

A K-12 cross-disciplinary Learning Progression Model (LPM) — biology, social studies, and computer science — built as a reference/pilot implementation of the [OpenEvo Concept Base (OECB)](https://github.com/openevo-ccs/conceptbase).

**Status:** draft / Phase 1 pilot (`status: proposed` in [`lpm.yaml`](lpm.yaml)) — not a finished curriculum, a worked example of how a dependent repository is built against OECB.

## What this is

Three strands — inheritance/variation/selection across systems, agency/development/niche construction, and culture/technology/collective systems — built **exclusively** on the `OE-INTERDISCIPLINARY-v1.0.0` controlled vocabulary, which (unlike `BIO-CORE-v1.0.0`) includes Agency, Niche Construction, and a multiply-defined Selection concept spanning biology, culture, education, and AI framings. That's a deliberate contrast with [`bio-core-k12`](https://github.com/openevo-ccs/bio-core-k12)'s single-vocabulary, agency-free sibling LPM — see OECB's [Why Pluralism Matters](https://github.com/openevo-ccs/conceptbase#why-pluralism-matters) for why the two are intentionally built from different vocabularies rather than reconciled into one.

Strand 1's and Strand 2's cross-domain claims (Selection as a transferable mechanism across biology/culture/AI; Agency in designed systems) are the specific claims checked against real external standards in OECB's [Selection cross-domain case study](https://github.com/openevo-ccs/conceptbase/blob/main/docs/design-notes/selection-cross-domain-case-study.md) — worth reading alongside this repo if you want to see how the alignment layer holds this LPM's claims accountable rather than just taking its own confidence at face value.

See [`lpm_doc.md`](lpm_doc.md) for the original authoring notes on how vertical/horizontal coherence were engineered across both pilot LPMs, and gaps flagged at the time (some since resolved — e.g. the alignment records it says don't exist yet now do, see `conceptbase/alignments/`).

## How this fits together

```
lpm.yaml                    # OE-LPM-000002 — manifest: identity, conceptbase deps, strand list
lpm_doc.md                  # Authoring notes on coherence design and known gaps
strands/
  strand-201-*.yaml         # OE-STRAND-000201
  strand-202-*.yaml         # OE-STRAND-000202
  strand-203-*.yaml         # OE-STRAND-000203
```

`lpm.yaml`'s `conceptbase:` block pins the exact ontology and vocabulary versions this LPM was built against — see [OECB's Quickstart](https://github.com/openevo-ccs/conceptbase#quickstart) for what that manifest shape means and how to author your own. This repo is indexed in OECB's `registry/lpm-index.json`, so `OE-LPM-000002` resolves live at [`https://www.w3id.org/openevo/lpm/OE-LPM-000002`](https://www.w3id.org/openevo/lpm/OE-LPM-000002).

## Validating locally

Every strand file validates against OECB's `schemas/strand.schema.yaml`, and `lpm.yaml` against `schemas/lpm.schema.yaml`. From a checkout of `conceptbase` alongside this repo:

```bash
python scripts/validate.py schemas/lpm.schema.yaml ../oe-interdisciplinary-k12/lpm.yaml
python scripts/validate.py schemas/strand.schema.yaml ../oe-interdisciplinary-k12/strands/*.yaml
```

**This runs automatically, too:** [`.github/workflows/validate.yml`](.github/workflows/validate.yml) checks out `conceptbase`'s `main` branch alongside this repo and runs these exact two commands on every PR (and on push to `main`) — the badge at the top of this README reflects the latest run. It's schema validation only, not full pin/deprecation checking (that's still Phase 4 upstream, see [conceptbase's Roadmap](https://github.com/openevo-ccs/conceptbase#roadmap)) — but it means a strand file that stops validating gets caught before merge, not whenever someone happens to run the command by hand.

## License

[CC-BY-NC-SA-4.0](LICENSE), matching the `OE-INTERDISCIPLINARY-v1.0.0` vocabulary this LPM is built on (see OECB [RFC-0004](https://github.com/openevo-ccs/conceptbase/blob/main/proposals/0004-relicense-content-cc-by-nc-sa.md)).
