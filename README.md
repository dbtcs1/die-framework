# Dimensional Intelligence Expansion (DIE)

**Principal Investigator:** Chung Huang Chew (r4all)
**Version:** 1.4 | May 2026
**Status:** Preprint FINAL v4 — arXiv submission in progress

---

## What is DIE?

A research framework proposing that a self-replicating peer-to-peer AI agent
mesh, seeded by human orchestrators and powered by abundant energy, achieves
dimensional reach that is functionally equivalent to — and in scaling velocity
superior to — centralised quantum computing architectures.

---

## Provenance Record

| Layer | Record | Status |
|---|---|---|
| Conceptual origin | Bitcoin inscription `7ef05490f16da89aa156f2d37ef780826bc51347b116f89c955691f535b1cf73i0` | ✅ Complete |
| Academic archive v1 | Zenodo [10.5281/zenodo.19888889](https://zenodo.org/records/19888889) — April 2026 | ✅ Complete |
| Academic archive v2 | Zenodo [10.5281/zenodo.20407711](https://zenodo.org/records/20407711) — FINAL v4, May 2026 | ✅ Complete |
| arXiv preprint | cs.AI / cs.MA / cs.CR / nlin.AO submission | 🔄 In progress |
| Git history | This repository | ✅ Ongoing |

---

## Tools

Two paired artifacts in `tools/` make the framework droppable into any AI agent stack:

- [`DIE-system-prompt-v1.md`](tools/DIE-system-prompt-v1.md) — the **system message**. Installs the DIE evaluation frame (Core Axiom, Architecture Note, Tone Bounds, D1–D5 protocol, Chapter 1–6 map, SS1/SS2 snapshot protocol) as standing context. Always-latest on `main`; current version: v1.2 (commit `a24e383`).
- [`DIE-user-prompt-template-v1.md`](tools/DIE-user-prompt-template-v1.md) — the **user message** template. An eight-block reusable structure for applying the protocol to any new source (podcast, paper, article, talk, document). Current version: v1.0 (commit `41c4a4e`).

Worked example: see [the AlphaFold post](https://thinkmasters.com/alphafold-through-the-die-lens-and-what-the-droppable-system-prompt-actually-installs) — DIE-framed analysis of Veritasium's AlphaFold episode (27 May 2026) produced by running this template against the v1.1 system prompt.
