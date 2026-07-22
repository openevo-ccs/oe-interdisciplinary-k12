# Contributing to oe-interdisciplinary-k12

**Status:** This repository is a reference/pilot Learning Progression Model (LPM) built against
the [OpenEvo ConceptBase](https://github.com/openevo-ccs/conceptbase) (OECB) — it contains
curriculum content (strands, objectives), not vocabulary or schema definitions. Changes to the
underlying `OE-INTERDISCIPLINARY` vocabulary, concepts, or competencies go through conceptbase's
own [CONTRIBUTING.md](https://github.com/openevo-ccs/conceptbase/blob/main/CONTRIBUTING.md) and
RFC process, not here.

## Before you start

Read the README and [`lpm_doc.md`](lpm_doc.md) for orientation, and [`lpm.yaml`](lpm.yaml) for
this LPM's declared status and vocabulary dependency. This repo is `status: proposed` (Phase 1
pilot per the README) — expect content gaps and stub objectives, not a finished curriculum. Its
agency-inclusive vocabulary is a deliberate contrast to `bio-core-k12`'s — read `lpm_doc.md`
before assuming the two repos should converge on identical modeling choices.

## Proposing a change

- **Content changes** (a strand's structure, an objective's wording, grade-band placement): open
  a PR against the relevant file in [`strands/`](strands/) describing what changed and why. One
  reviewer approval before merge — no heavier process exists for this repo today.
- **New content that needs a vocabulary term that doesn't exist yet** (a new Concept, Competency,
  or relation): that goes through conceptbase's RFC process first — this repo can only reference
  identifiers conceptbase has already accepted, per OECB's registry model.

## License

Content is CC-BY-NC-SA-4.0 ([`LICENSE`](LICENSE)), matching the `OE-INTERDISCIPLINARY-v1.0.0`
vocabulary this LPM is built on (see conceptbase [RFC-0004](https://github.com/openevo-ccs/conceptbase/blob/main/proposals/0004-relicense-content-cc-by-nc-sa.md)).
Contributions are under the same license.

## Questions

Open a GitHub issue, or reach out to the OpenEvo Computational Curriculum Studies Lab
([openevo.eva.mpg.de](http://openevo.eva.mpg.de)).
