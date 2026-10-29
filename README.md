# Hi, I'm Tan Yongjun (谭咏俊)

**Agent / LLM application development** · 南京大学 · 2028 届

I build agents where the model handles intent, and the code owns the decisions that must be correct.
I also measure them — every number below is recomputable from the repo, without an API key.

## Two flagship projects

### 1. [return-agent-lab](https://github.com/tyj-618/return-agent-lab) — bounded tool-using agent

Turns a vague return request into a correct, confirmed, auditable return.

- **Bounded tool loop** — 4 tools, 8 turns / 10 calls / 60s, 6 stop reasons, JSONL trace
- **Safety by construction** — identity injected, order snapshot hash, confirmation bound to the
  plan, 30-min TTL
- **Idempotent writes** — one transaction, unique confirmation, `already_exists` on retry
- **Evaluated** — 10 fixed cases ×3 runs: **30/30**; fixed-flow baseline **9/10**;
  3.7k tokens / 2.6s per case; **102 tests**

### 2. [clause-proof](https://github.com/tyj-618/clause-proof) — auditable extraction agent

Reviews contract clauses and emits a judgment, a character-level citation, a confidence, and a
routing decision — so every conclusion can be checked against the source text.

- **Citations verify themselves** — 96.0% of quotes locate verbatim in the source; the remaining
  4% are counted and reported, not hidden
- **Measured, not asserted** — 300 queries on CUAD dev: **93.2%** macro accuracy
  (95% CI 0.900–0.961), **10.0%** abstention, global ECE 0.046
- **Routing under a review budget** — at 11.3% human review, auto-passed items reach 94.7% accuracy
- **Reproducible offline** — all metrics recomputable from committed JSONL, no API key needed;
  **458 tests**

**The two projects answer different halves of one question: is the agent correct, and can you prove it?**
One is an online, multi-turn agent with hard runtime boundaries; the other is an offline evaluation
harness built so that claims are falsifiable.

## How I work

Contracts first, then implementation. Each task carries acceptance criteria before code is written;
implementation and review stay separated; defects are written down instead of quietly patched.

- clause-proof: [16 engineering lessons](https://github.com/tyj-618/clause-proof/blob/main/docs/lessons.md) ·
  [6 ADRs](https://github.com/tyj-618/clause-proof/blob/main/docs/adr/README.md) ·
  [evaluation record](https://github.com/tyj-618/clause-proof/blob/main/docs/experiments/2026-10-28-m1-baseline.md)
- return-agent-lab: [AI collaboration](https://github.com/tyj-618/return-agent-lab/blob/main/docs/ai-collaboration.md) ·
  [defect ledger](https://github.com/tyj-618/return-agent-lab/blob/main/docs/defect-ledger.md) — 13 documented issues ·
  [evaluation report](https://github.com/tyj-618/return-agent-lab/blob/main/docs/evaluation.md)

## Stack

- **Agent / LLM**: tool calling, agent loop & stop conditions, context management, structured output,
  evaluation harness
- **Language**: Python, Java
- **Data**: SQLite, MySQL, Elasticsearch, Redis
- **Infra**: Docker, Git

## Earlier work

- [UniNook](https://github.com/tyj-618/UniNook) — campus community: geo-scoped feed, hybrid RAG
  assistant, Spring Boot + Vue
- [OfferForge](https://github.com/tyj-618/OfferForge) — AI interview coach
- [agent-skills](https://github.com/tyj-618/agent-skills) — portable coding-agent skills for
  evidence-first delivery
