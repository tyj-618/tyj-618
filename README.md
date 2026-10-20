# Hi, I'm Tan Yongjun (谭咏俊)

**Agent / LLM application development** · 南京大学 · 2028 届

I build agents where the model handles intent, and the code owns the decisions that must be correct.

## Featured: [return-agent-lab](https://github.com/tyj-618/return-agent-lab)

A return-request agent: turns a vague request into a correct, confirmed, auditable return.

- **Bounded tool loop** — 4 tools, 8 turns / 10 calls / 60s, 6 stop reasons, JSONL trace
- **Safety by construction** — identity injected, order snapshot hash, confirmation bound to the plan, 30-min TTL
- **Idempotent writes** — one transaction, unique confirmation, `already_exists` on retry
- **Evaluated** — 10 fixed cases ×3 runs: **30/30**; fixed-flow baseline **9/10**; 3.7k tokens / 2.6s per case; **102 tests**

## How I work with AI

AI writes the implementation. Contracts, review and acceptance stay on my side.

- [AI collaboration](https://github.com/tyj-618/return-agent-lab/blob/main/docs/ai-collaboration.md)
- [Defect ledger](https://github.com/tyj-618/return-agent-lab/blob/main/docs/defect-ledger.md) — 13 documented issues (11 defects + 2 design trade-offs)
- [Metrics](https://github.com/tyj-618/return-agent-lab/blob/main/docs/metrics.md)
- [Evaluation report](https://github.com/tyj-618/return-agent-lab/blob/main/docs/evaluation.md)

## Stack

- **Current**: Python · SQLite · OpenAI-compatible APIs · unittest · Git
- **Earlier**: Java / Spring Boot · Vue · Elasticsearch

## Earlier work

- [UniNook](https://github.com/tyj-618/UniNook) — campus community with a RAG assistant
- [OfferForge](https://github.com/tyj-618/OfferForge) — AI interview coach
