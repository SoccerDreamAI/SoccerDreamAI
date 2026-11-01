# SoccerDream AI

**A multi-agent research team that argues with itself, cross-checks every claim, and runs its own post-mortem — before it publishes a single conclusion.**

[English](README.md) · [简体中文](README.zh-CN.md)

[![Source-available](https://img.shields.io/badge/status-source--available-orange.svg)](https://github.com/SoccerDreamAI/soccerdream-experts/blob/main/NOTICE.md)
[![Not a betting product](https://img.shields.io/badge/research_framework-not_a_betting_product-red.svg)](https://github.com/SoccerDreamAI/soccerdream-experts/blob/main/NOTICE.md#8-no-warranty-no-advice)
[![License: BUSL-1.1](https://img.shields.io/badge/license-BUSL--1.1-blue.svg)](https://github.com/SoccerDreamAI/soccerdream-experts/blob/main/NOTICE.md)

[soccerdreamai.com](https://soccerdreamai.com) · [The framework](https://github.com/SoccerDreamAI/soccerdream-experts) · [Why averaging fails](https://dev.to/soccerdreamai/why-a-multi-agent-system-must-not-average-3p5d) · [Discussions](https://github.com/SoccerDreamAI/soccerdream-experts/discussions)

---

## What we are doing

Most "AI analysis" products give you one model and one confident answer. For any question
where being wrong is expensive, that is the wrong shape — the confidence is doing more work
than the analysis.

So what we publish is the **shape of the team**: several specialists with genuinely different
priors, a structured disagreement protocol, and a review stage that is allowed to overturn the
conclusion.

- Every rule they follow is readable.
- You can build your own team from the same schema.
- What you cannot see is the part we consider the product.

## The one rule

> **Disagreement is escalated, never averaged.**

Averaging is the identity operation when the members agree, and at full strength when they
disagree — which is precisely backwards. At the moment two informed readers contradict each
other, the only informative fact in the run is *that they contradicted each other*. A mean
destroys it and returns a conclusion nobody proposed and nobody would defend.

So a disagreement goes to a challenge stage instead. Each side either cites its evidence or
**withdraws in writing**, and the withdrawal is recorded as the output of that round. If neither
withdraws, the item ships marked `unresolved`.

An honest "we could not settle this" beats a fabricated midpoint.

## What is public, and what is not

| | Contents | Public |
|:--|:--|:--:|
| Personas | Four specialists under a fixed `Prior → Method → Evidence → Refusal` contract | ✅ |
| Orchestration | The `teams/` schema and a runnable example | ✅ |
| Reasoning | The architecture doc, including the five failure modes we hit | ✅ |
| Training prompts | The model-specific wording that makes the personas behave | ❌ |
| Evaluation weights | What a claim has to clear before it survives review | ❌ |
| Data pipeline | Live adapters, normalisation, and settlement logic | ❌ |

This repository is **source-available, not open source**. We say so on line one rather than
letting you install it and discover it: a repository that looks complete and is not damages a
project more than the missing code ever would.

That is not modesty. The personas are useful on their own; the part that makes them reliable is
the part we kept.

## Start here

1. **Read the reasoning** — [Why a multi-agent system must not average](https://dev.to/soccerdreamai/why-a-multi-agent-system-must-not-average-3p5d)
2. **Read the architecture** — [docs/architecture.md](https://github.com/SoccerDreamAI/soccerdream-experts/blob/main/docs/architecture.md)
3. **Build a team** — [teams/](https://github.com/SoccerDreamAI/soccerdream-experts/tree/main/teams)
4. **Show yours** — [Discussions](https://github.com/SoccerDreamAI/soccerdream-experts/discussions/4)

If you only have thirty seconds: the failure mode that catches everyone is **independence
leaking through the runtime**. The prompts look clean, but every member is reading a shared
buffer — so you paid for four estimates and received one.

---

<sub>This is an analysis framework. It does not predict outcomes, is not advice, and is not
intended for wagering. SoccerDream AI and SoccerDream Expert Team are unregistered marks;
forks must be renamed and must not imply endorsement. See
[TRADEMARK.md](https://github.com/SoccerDreamAI/soccerdream-experts/blob/main/TRADEMARK.md).</sub>
