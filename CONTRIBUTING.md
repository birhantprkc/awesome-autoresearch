# Contributing to awesome-autoresearch

Thanks for helping improve this list.

The goal is simple: collect public, concrete autoresearch use cases and make them easy to scan.

## What belongs here

We accept public examples such as:

- GitHub repositories
- X threads or posts
- Blog posts and articles
- Project homepages or public write-ups

A good entry clearly shows:

- **Scenario**: where autoresearch is used
- **Method**: what the autoresearch loop actually does
- **Value**: why it matters

It should also satisfy at least one of these:

- explicitly uses the term `autoresearch`
- explicitly cites Karpathy's autoresearch
- clearly implements a modify → verify → keep/discard → repeat loop

If a project is merely an AI agent for research, monitoring, scraping, summarization, or workflow automation, it probably does **not** belong here.

## What does not belong here

Please do not submit:

- Generic research agents or monitoring agents with no explicit autoresearch loop
- Generic multi-agent systems with no keep/discard verification pattern
- Plain RAG, scraping, summarization, or dashboard projects unless they explicitly operate as autoresearch loops
- Pure conceptual discussion
- Tool lists without a real workflow
- Marketing fluff with no concrete example
- Private, dead, or inaccessible sources
- Multi-paragraph explanations inside category files
- Repositories that only *describe* an autoresearch loop without implementing one
- Repositories whose documentation outweighs their code while claiming to be tools
- Launch, funding, or press announcements presented as implementations

For AI-assisted work, project depth, and submission-rate rules, see [AI-assisted work, and bulk submissions](#ai-assisted-work-and-bulk-submissions).

## Core rules

### 1. One entry, one category — no cross-posting

Every entry lives in exactly one category file. When a project straddles multiple categories, choose the one closest to its direct application domain and commit only there. Never add the same entry to two category files.

If you're torn between two categories, ask: "What is the end user actually doing?" — that's the category.

### 2. Keep every entry to one sentence

Every entry must stay on a single bullet line.

### 3. Use autoresearch-domain classification

Choose the category based on the direct autoresearch application domain, not on generic labels like "agent", "research", or "monitoring".

### 4. Prefer clarity over cleverness

If a reader cannot understand the use case in one quick pass, rewrite it.

### 5. Prefer fewer, stronger entries

High-signal curation is more important than volume.

### 6. Depth over surface area

An entry has to describe something that **runs**, not something that is described. Before submitting, make sure:

- the repository implements the loop it claims — a modify → measure → keep-or-discard step in the code, not only in the prose;
- there is at least one runnable check or committed result that would change if the logic broke — a benchmark harness, a results file, a test, or a public demo;
- any number in your entry (speedup, accuracy, cost, time saved) is traceable to the linked page.

If a project is mostly prompt documents, skills, or templates, that is fine — but submit and describe it as such. Do not present a prompt pack as a runner.

## AI-assisted work, and bulk submissions

AI-assisted development is welcome here. Plenty of listed projects were built with coding agents, and that is not a reason to exclude them. It does change what the reviewer needs from you.

### Disclose AI generation

If a project was generated or substantially written by an AI system, say so in the pull request, and preferably in the repository. Disclosure is not a penalty — it sets the review bar honestly, and it tells maintainers to check depth rather than authorship.

Undisclosed generation usually becomes obvious anyway: a shared scaffold, a single bulk commit, documents far outweighing code. Being caught that way costs more trust than the disclosure would have.

### Do not ship a scaffold as evidence

One `AGENTS.md` / `CLAUDE.md` / `STATE.md` / `CHANGELOG.md` template reused across several repositories does not make any of them more complete. Neither does a README that documents features the code does not implement, or a results table with no artifact behind it.

### Submission rate

Bulk submission is the most common way this list loses signal — and this list is collected by automated sweeps, so it is exposed to it more than most.

- **One entry per pull request.** Do not bundle unrelated projects.
- **At most three entries per author per rolling seven days.** This is a review-priority rule, not a ban: entries beyond it are queued to a later cycle, not rejected on sight.
- **Projects released together are reviewed individually.** Being in the same batch grants no shared credibility, and a weak member can hold up a strong one.
- **A shared release date is treated as a risk signal**, not as momentum.
- **Announcing a project is not evidence it exists.** A launch thread, a press release, or a funding announcement is not an implementation; it belongs in `related-practices-discussions.md`, if anywhere.

Maintainers may accept a project with a caveat when the code is real but depth is unproven, and may decline one member of a batch while accepting its siblings.

## Entry format

Use this exact format:

```md
- [Name](URL) - Industry: one-sentence description of the autoresearch use case.
```

### Good examples

```md
- [AutoKernel](https://example.com) - GPU optimization: applies Karpathy-style autoresearch to kernel bottlenecks, benchmarking each change and keeping only verified speedups.
- [Claudini](https://example.com) - AI safety research: uses an autoresearch-style loop to discover and benchmark stronger LLM attack algorithms.
- [Autoresearch Genealogy](https://example.com) - Genealogy: runs `/autoresearch` prompts to expand family trees, verify claims, and keep a structured evidence-backed vault.
```

### Weak examples

```md
- [Cool Tool](https://example.com) - AI agent for research.
```

Why weak:

- No concrete scenario
- No explicit autoresearch loop
- No method
- No outcome
- Too vague to classify

## Where to place entries

Add entries to exactly one of these category files:

- `categories/scientific-research.md` — science, medicine, lab work
- `categories/software-systems-optimization.md` — performance, kernel, compiler, app optimization
- `categories/evaluation-red-teaming.md` — testing, benchmarking, jailbreaking, hardening
- `categories/finance-trading.md` — trading strategies, market analysis, fintech
- `categories/personal-knowledge-humanities.md` — genealogy, personal wikis, humanities
- `categories/knowledge-base-rag-preparation.md` — RAG prep, knowledge curation for retrieval systems
- `categories/market-research.md` — market structure, pricing, competitive landscape
- `categories/workflow-automation.md` — embedded operational loops handing results to downstream actions
- `categories/infra-skills-forks.md` — engines, harnesses, ports, skills, dashboards, orchestration
- `categories/related-practices-discussions.md` — threads, interviews, articles (no standalone repo)

If an example could fit multiple categories, choose the one that represents the direct autoresearch application domain. When in doubt, follow this decision flow:

```
Is there a standalone repo?
  ├─ No  → related-practices-discussions.md
  └─ Yes → What does the user actually accomplish?
            ├─ Science/medicine/lab          → scientific-research.md
            ├─ Performance/kernel/app tuning  → software-systems-optimization.md
            ├─ Testing/benchmarking/attacking → evaluation-red-teaming.md
            ├─ Trading/market finance         → finance-trading.md
            ├─ Personal wiki/genealogy        → personal-knowledge-humanities.md
            ├─ RAG/retrieval pipeline prep     → knowledge-base-rag-preparation.md
            ├─ Market landscape research       → market-research.md
            ├─ Operational loop for automation → workflow-automation.md
            └─ Engine/harness/port/skill       → infra-skills-forks.md
```

`README.md` is auto-generated from category files — never edit it directly.

## Style guidance

- Keep wording concrete.
- Name the industry or domain explicitly.
- Describe the autoresearch loop, not just the tool.
- Avoid buzzwords unless the source itself depends on them.
- Do not add long commentary under entries.

## Pull request checklist

Before submitting, confirm:

- [ ] The source is public and accessible.
- [ ] The entry is one sentence.
- [ ] The source is directly about autoresearch, not just a generic research agent.
- [ ] The entry explains scenario + method + value.
- [ ] The category reflects the direct autoresearch use case.
- [ ] The wording is concise and easy to scan.
- [ ] The repository actually implements the loop (not a README-only claim).
- [ ] There is at least one runnable check or committed result, or the entry says plainly that there is not.
- [ ] Any number in the entry traces back to the linked page.
- [ ] AI generation is disclosed, if it applies.
- [ ] This is not more than my third entry in a rolling seven-day window.
