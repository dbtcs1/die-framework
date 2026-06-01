<!--
Title:       DIE Protocol — Reusable User-Prompt Template
Version:     v1.0
Date:        2026-06-01
Author:      Chung Huang Chew (r4all) / Thinkmasters
Status:      Live — open for use; cite source when deploying
Derived:     Generalised from the AlphaFold post user-prompt (27 May 2026)
Paired with: DIE-system-prompt-v1.md (always-latest on main)
-->

# DIE Protocol — Reusable User-Prompt Template

A copy-paste **user message** template for applying the DIE framework to any new source — podcast, paper, article, talk, document. Pair with the current-latest DIE system prompt as your system message; this template is your user message.

Background on what the DIE system prompt actually installs (frame vs. library, the four architectures of "installed context"): see [the AlphaFold worked example](https://thinkmasters.com/alphafold-through-the-die-lens-and-what-the-droppable-system-prompt-actually-installs).

---

## How to use

1. Open your AI agent (Claude, GPT, Gemini, a local Llama or Qwen).
2. **System message:** paste the entire content of [`DIE-system-prompt-v1.md`](https://github.com/dbtcs1/die-framework/blob/main/tools/DIE-system-prompt-v1.md) (always latest on `main`).
3. **User message:** paste the template in the next section. Fill in the `<<...>>` fields with your source's metadata and content. Delete optional sections you don't need.
4. Send. The agent returns a DIE-framed analysis along the canonical structure.

The template has **eight numbered blocks**. Blocks `[1]`–`[4]` are the **minimum viable run** (source metadata + provenance + action + core tasks). Blocks `[5]`–`[7]` are **upgrades** for prompt-audit runs, operator integration, and blog deliverables. Block `[8]` is the source content itself.

---

## Template — copy from inside the fence ↓

```
=== DIE PROTOCOL APPLICATION ===

[1] SOURCE METADATA
    Title:        <<source title>>
    URL:          <<source URL or DOI>>
    Date:         <<YYYY-MM-DD of publication>>
    Type:         <<podcast | paper | article | talk | doc | dataset>>
    Length:       <<duration in minutes or word count>>
    Author(s):    <<creator names>>

[2] PROVENANCE ANCHORS — snapshot the artifacts at time of this run
    System prompt audited:    github.com/dbtcs1/die-framework/blob/<<commit hash>>/tools/DIE-system-prompt-v1.md
    System prompt version:    <<e.g. v1.1>>  (latest on main at time of run)
    Framework governance:     github.com/dbtcs1/die-framework/blob/<<commit hash>>/program.md
    program.md version:       <<e.g. v1.4>>
    Preprint / archive:       zenodo.org/records/<<id>>
    Repository:               github.com/dbtcs1/die-framework
    Run timestamp:            <<YYYY-MM-DD HH:MM, timezone>>
    Operator:                 <<name / handle / project>>

[3] ACTION
    Please review, analyse, critique and summarise the source above in the
    context of AI, AI Agents, and the DIE Framework. Apply the protocol below.
    Cite specific moments / quotes / data points from the source for every
    verdict. Where a protocol cannot be applied to this source, say so
    explicitly — do not force-fit.

[4] CORE TASKS

    a) CHAPTER MAPPING — for each of Ch1, Ch2, Ch2.5, Ch3, Ch4, Ch5, Ch6:
       does this source illustrate the chapter? Cite specifics. If a chapter
       does NOT map, say so.

    b) D1–D5 PROTOCOL AUDIT — per-protocol verdict (✅ Pass / ⚠️ Partial /
       ❌ Fail) with reasoning. For D1 specifically, provide an ELI5 of
       (i) what is the shadow, (ii) what cast it, (iii) what the protocol
       surfaces that the source narrative hides. Make the reasoning visible
       in the body, not buried.

    c) SS1 → SS2 SNAPSHOT — what did the relevant field know BEFORE the
       events / claims in this source? What does it know AFTER? Tabulate
       the delta. Quantify where possible (corpus size, cost, time, scale).

    d) C1–C4 EXTERNAL VALIDATION — does this source demonstrate any of DIE's
       four falsifiable conditions?
         C1  Memory accumulation improves output (trunk thickening)
         C2  Memory loss degrades output (sapling problem)
         C3  Values bounds hold at mesh scale (DNA propagation)
         C4  Emergent summaries exceed inputs (emergence)
       Per-condition verdict with reasoning. C3 typically requires an agent
       mesh; if absent, say "not tested" and explain why.

    e) LESSONS FOR DIE — what should the preprint absorb from this source?
       Numbered list. Cite the specific chapter, condition, or claim affected.

    f) CRITIQUE — what the source does NOT discuss that DIE would surface.
       Where is the source wrong, biased, sponsored-distorted, or
       silently-political? Be direct.

[5] STRESS-TEST BLOCK — optional; include when auditing the prompt itself

    g) Did the prompt produce useful framing on this source? Give specific
       examples of where it succeeded and where it fell short.

    h) ELI5 — what is the prompt actually DOING internally? Does it reference
       the artifacts linked in [2] (program.md, preprint, repo) or ONLY what
       is literally in the prompt text? Be precise about scope.

    i) Which "installed-context" architecture is in play —
         0  Frame only (prompt text only; references not followed)
         1  RAG-backed (vector store of corpus; on-demand retrieval)
         2  Tool-augmented (web_fetch / filesystem; lazy retrieval)
         3  Layered context (preprint + program.md preloaded eagerly)
       See §5 of the AlphaFold post for the taxonomy.

    j) Gap → next version. What does this audit suggest for the next prompt
       version? Mark as KIV (keep in view).

[6] OPERATOR INTEGRATION — optional; include only if relevant

    k) INFRASTRUCTURE MAPPING — where will the operator's VM stack fit?
       Standard public-facing labels:
         VM2203  local LLMs (inference + DIE frame application)
         VM2208  LiveKit ingest (audio → transcript, EN/ZH/JA)
         VM2209  Thinkmasters website (publish + provenance append)
         VM2210  OpenClaw sandbox (multi-agent variant testing)
         VM2262  Proxy / egress (TLS, topology hiding)
       Sketch the pipeline for processing this source through the stack.

    l) MONETISATION — where / how can thinkmasters.com or the OpenClaw stack
       use this source's approach or automations? Identify low-hanging fruit.
       Map to existing rails where possible (USDC / x402 / ERC-8004).

[7] DELIVERABLE — optional; include when the run targets a publishable artifact

    m) Assemble a drop-into-thinkmasters markdown blog post following the
       canonical structure:
         - Subtitle (always-latest framing)
         - § The question
         - § 1 Chapter map
         - § 2 D1–D5 audit (with D1 ELI5 visible in body)
         - § 3 SS1 → SS2 snapshot
         - § 4 C1–C4 external validation
         - § 5 What the droppable layer actually installs
         - § 6 Pipeline architecture (VM22xx series only — internal numbers stay private)
         - § 7 Try it yourself (reusable template + always-latest footnote)
         - § 8 Lessons for DIE
         - Provenance block (table)
       Footnote the prompt version + commit hash per [2] at the top of the
       post.

[8] SOURCE CONTENT
    Paste transcript, paper body, article text, or dataset description below
    the line. For long documents, paste the most analytically dense portion;
    summarise the rest in [1].

────────────────────────────────────────────────────────────────────
<<paste source content here>>
────────────────────────────────────────────────────────────────────
```

(↑ end of template)

---

## Worked example — the AlphaFold instance

Here is how this template was filled in for the AlphaFold post (only `[1]`, `[2]`, and `[3]` shown in full; the rest follows the template verbatim).

```
[1] SOURCE METADATA
    Title:        AlphaFold — The Most Useful Thing AI Has Ever Done (Veritasium)
    URL:          https://www.youtube.com/watch?v=P_fHJIYENdI
    Date:         2026-05-27
    Type:         podcast / long-form video essay
    Length:       ~24 minutes
    Author(s):    Derek Muller (Veritasium); featuring John Jumper, David Baker

[2] PROVENANCE ANCHORS
    System prompt audited:    github.com/dbtcs1/die-framework/blob/f1faa12/tools/DIE-system-prompt-v1.md
    System prompt version:    v1.1 (latest on main at time of run)
    Framework governance:     github.com/dbtcs1/die-framework/blob/main/program.md
    program.md version:       v1.4
    Preprint / archive:       zenodo.org/records/19888889
    Repository:               github.com/dbtcs1/die-framework
    Run timestamp:            2026-06-01 09:00 SGT
    Operator:                 r4all / Thinkmasters

[3] ACTION
    [verbatim from template]

[4]–[7]  All blocks included (this was a full prompt-audit + blog-deliverable run)

[8] SOURCE CONTENT — Veritasium transcript pasted below the line
```

The output of that run lives at: `thinkmasters.com/alphafold-through-the-die-lens-and-what-the-droppable-system-prompt-actually-installs`.

---

## Notes on use

**Always-latest discipline.** Block `[2]` always links to `main` for the body reference, and pins the commit hash + version live AT THE TIME OF THE RUN. Readers can reproduce by clicking the commit-hash link; future runs use the current `main`. Mutable links in body text, immutable snapshots in `[2]` and in footnotes.

**Minimum viable run.** Blocks `[1]`–`[4]` are sufficient for a standard DIE-framed analysis of any source. The agent will return chapter mapping, D1–D5 audit, SS1/SS2 snapshot, C1–C4 validation, lessons, and critique. Blocks `[5]`–`[7]` are upgrades for prompt audits, operator integration, and blog deliverables.

**Drop sections you do not need.** Block `[5]` is only relevant when auditing the prompt itself, not when applying it to a new source. Block `[6]` is only relevant inside the operator's stack (VM22xx series). Block `[7]` is only relevant when the deliverable is a blog post.

**Citation discipline.** Every reference in `[2]` should ultimately resolve to an immutable artifact — commit hash, DOI, or BRC-20 inscription. This is the same Chapter 4 (Blockchain Coordination) discipline DIE applies to its own provenance. Branch pointers (`main`, `HEAD`) are mutable; commit hashes are cryptographic fingerprints of file content and cannot change.

**Reproducibility.** Two runs of this template against the same source and the same `[2]` snapshot should produce structurally equivalent analyses — same protocol verdicts, same chapter mappings, same SS1/SS2 deltas. Stylistic variation is expected; structural variation is a bug worth investigating (it implies either prompt drift, model drift, or source ambiguity).

**Self-application.** This template can itself be analysed using this template — apply the DIE protocol to the template as the source. Useful for catching design drift in the template itself. Future versions of this template (`v1.1`, `v1.2`, …) should be reviewed this way before publication.

---

## Versioning

This template is itself versioned and follows the same always-latest + footnote-snapshot discipline as the system prompt.

- **v1.0 — 1 June 2026.** First publication. Generalised from the AlphaFold post user-prompt (27 May 2026). Proposed canonical location: `github.com/dbtcs1/die-framework/blob/main/tools/DIE-user-prompt-template-v1.md`.

Future versions will be tracked at the same path with commit-hash provenance.

---

*Principal Investigator: Chung Huang Chew (r4all). Cite source when deploying. Derivative work must preserve this header block.*
