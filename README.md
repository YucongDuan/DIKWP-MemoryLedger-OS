# DIKWP MemoryLedger OS

**Open-source AI memory sovereignty layer, purpose-continuity ledger, and persistent-context governance toolkit.**

DIKWP MemoryLedger OS helps teams and individuals decide what an AI assistant or AI agent may remember, why it may remember it, how long it may retain it, what evidence supports it, when it must be reviewed, and how it can be exported or forgotten.

It is designed as the third open-source application in the DIKWP practical stack:

1. **DIKWP AnswerGraph Studio** — make brand and knowledge assets readable as verified AI answer candidates.
2. **DIKWP IntentGuard OS** — block prompt injection, unsafe tool use, and P-layer intent drift before action.
3. **DIKWP MemoryLedger OS** — govern persistent memory, purpose continuity, consent, expiry, provenance, and deletion.

## Why this exists

Persistent memory is becoming a mainstream AI feature. That creates a new governance problem: memory is not just stored text. It is a purpose-bearing, time-carrying, identity-affecting semantic object. A bad memory can create future errors; an over-retained memory can violate privacy; a poisoned memory can corrupt downstream agent behavior; an unreviewed organizational memory can silently preserve obsolete standards.

DIKWP MemoryLedger OS treats every proposed memory as a DIKWP object:

```text
C = (D, I, K, W, P, R)
D: data fragment or observed statement
I: relation, context, entity, source, time
K: mechanism, rule, project knowledge, task knowledge
W: value, risk, policy, sensitivity, consent, retention judgment
P: purpose, allowed use, intended future action support
R: reliability, evidence, expiry, kill conditions, review status
```

## Key features

- Extract candidate memories from notes, transcripts, prompts, chat logs, support cases, project notes, and RAG outputs.
- Classify memory type: identity, preference, goal, constraint, project context, fact, policy, relationship, credential-like risk, health-like risk, financial-like risk, legal-like risk, sensitive personal data, organizational standard, and unsupported claim.
- Build a **Memory Evidence Ledger** with source spans, reliability, consent state, expiry and deletion status.
- Generate a **Purpose Continuity Map**: which goals, constraints and values must be remembered for long-running work.
- Detect **memory poisoning / memory overreach** patterns: "always remember", "ignore previous policy", "secretly store", "do not disclose", hidden instructions, unsupported facts, obsolete standards.
- Produce a **MCP-style context pack** that agents can consume as governed context.
- Produce a **DSAR-style export/delete bundle** for privacy and enterprise review workflows.
- Keep DIKWP / Yucong Duan attribution in open-source form through NOTICE and CITATION.cff.

## Quick start

```bash
python -m venv .venv
source .venv/bin/activate
pip install -e .

# Analyze a sample memory source
dikwp-memoryledger analyze examples/sample_memory_source.md --subject "Demo User" --out outputs/demo

# Or run with Python module syntax
python -m dikwp_memoryledger.cli analyze examples/sample_memory_source.md --subject "Demo User" --out outputs/demo
```

Generated files:

```text
outputs/demo/memory_ledger.json
outputs/demo/memory_risk_report.json
outputs/demo/purpose_continuity_map.json
outputs/demo/context_pack.json
outputs/demo/dsar_export.json
outputs/demo/recommendations.md
```

## Optional dashboard

```bash
pip install streamlit
streamlit run src/dikwp_memoryledger/app.py
```

The dashboard is optional. The core library and CLI use only Python standard-library modules.

## Governance boundary

This project does not provide surveillance, covert profiling, credential harvesting, hidden retention, or deceptive user tracking. It is a memory governance and audit tool. It is intended to make memory explicit, consented, reviewable, exportable and forgettable.

## License

MIT. See `LICENSE`.
