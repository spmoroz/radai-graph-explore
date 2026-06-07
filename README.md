# radai-graph — public dashboard

Live: **https://spmoroz.github.io/radai-graph-explore/**

Interactive read-only view of a typed knowledge graph that systematically tracks
AI deployments, products, vendors, and outcomes across peer-reviewed radiology
AI literature.

## What this is

`radai-graph` is a research artifact: a Python pipeline that extracts structured
entities and outcomes from peer-reviewed radiology AI publications into a typed
Pydantic ontology (v0.4 MVP — 12 entity types), deduplicates them by deterministic
slug + embeddings, and stores them as a queryable graph.

This repository hosts only the **published view** of the graph. It is rebuilt
periodically as new papers are extracted, prompts iterate, and the schema
matures. **Work in progress.**

## What's in the snapshot

The dashboard surfaces:

- **Publications** — peer-reviewed papers (Nature Medicine, Lancet Oncology, Lancet Digital Health, Nature Communications, Radiology, Radiology: AI, npj Digital Medicine, and others).
- **Vendors and products** — commercial AI tools and the companies behind them.
- **Deployments and infrastructure** — how products are integrated into clinical workflows.
- **Outcomes** — measured results (diagnostic accuracy, workflow efficiency, infrastructure latency, adoption, equity).
- **Cross-paper merges** — entities that independently surfaced across multiple papers and were automatically reconciled via slug.

## Caveats

- This is **not** peer-reviewed analysis. Findings reflect LLM-assisted extractions
  followed by human review against gold-standard fixtures, but they should not be
  cited as conclusions until the underlying extractions themselves are peer-reviewed.
- One or more publications under peer review are intentionally **omitted** from
  the published snapshot.
- The schema (v0.4 MVP) is frozen during this build cycle. Periphery entities
  (FailureMode, ImplementationBarrier, FundingSource, etc.) are deferred to v0.5.

## Project owner

**Sergey Morozov**, MD, PhD — radiologist, MedTech entrepreneur, AI-in-radiology researcher.
MedLogic SComm — Brussels, Belgium.
sergey@medlogic.co

## Status and roadmap

| Milestone | Status |
|---|---|
| v0.4 schema (12 entities, 12 relations) | ✅ Frozen for MVP build |
| 3-pass extraction pipeline (skeleton → outcomes → relations) | ✅ Validated |
| Cross-paper slug-based merge | ✅ Working |
| First operational efficiency analytics | ✅ Demonstrated |
| Periphery entities (FailureMode, RegulatoryEvent, etc.) | ⏳ v0.5 |
| Larger corpus (100+ papers) | ⏳ ongoing |
| Public query API | ⏳ post-MVP |

## License

The dashboard HTML is published under CC BY 4.0. The underlying source code
(extraction pipeline, schema, tests) is maintained privately during the MVP
phase and will be open-sourced after sufficient peer review of the methodology.

## Contact

For collaborations, methodological questions, or interest in the underlying
pipeline: sergey@medlogic.co
