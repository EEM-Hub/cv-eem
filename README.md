---
schema_version: "1.0"
type: eem
project_name: "reasons"
domain: []
license: mit
base_network: null
source_repos: []
beliefs_total: 1133
beliefs_in: 843
beliefs_out: 290
premises: 234
derived: 899
nogoods: 0
generator: ftl-reasons/0.48.0
---

# Reasons

## Stats

| Metric | Value |
|--------|-------|
| Total beliefs | 1133 |
| Status | 843 IN / 290 OUT |
| Premises (observations) | 234 |
| Derived (justified conclusions) | 899 |
| Nogoods (contradictions) | 0 |
| Retraction rate | 26% |
| Max derivation depth | 24 |

## How to Use

### Import into a reasons database

```bash
reasons init
reasons import-json network.json
```

### Query beliefs

```bash
reasons search "your query"
reasons explain <node-id>
reasons show <node-id>
```

## Files

| File | Description |
|------|-------------|
| `network.json` | Full belief network (machine-readable, portable) |
| `reasons.db` | SQLite database (gitignored, regenerate with `reasons import-json network.json`) |
| `README.md` | This EEM card |

## Quality

- 843 beliefs IN, 290 OUT
- 234 premises grounded in direct observations
- 899 derived beliefs justified via SL justifications
- 0 nogoods detected

## Exam Matrix

50-question exam across 19 CV topics, tested with beliefs context, no context (control), and agentic tool-calling mode.

| Model | With Beliefs | Control | Agentic | Delta |
|-------|-------------|---------|---------|-------|
| claude:opus | 48/50 (96%) | 48/50 (96%) | 48/50 (96%) | +0% |
| claude:sonnet | 48/50 (96%) | 45/50 (90%) | 48/50 (96%) | +6% |
| claude:haiku | 48/50 (96%) | 45/50 (90%) | 42/50 (84%) | +6% |

Beliefs lift Sonnet and Haiku to Opus-level performance (+6%). Agentic mode matches beliefs for Opus and Sonnet but degrades Haiku due to tool-calling protocol failures.

See `results/matrix-summary.md` for per-objective breakdown.

## Limitations

- Auto-generated card — review and customize for your use case

## License

mit
