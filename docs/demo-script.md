# Demo script (proposed)

## Goal
Show how Sentinel produces a governed RAG answer with an evidence pack for a software delivery scenario.

## Actors
- Dev lead requesting impact analysis for a code change.
- Sentinel orchestration responding through CLI or chat interface.

## Flow
1. **Setup**: point Sentinel to a sample repo and curated knowledge base; ensure policies are loaded.
2. **Prompt**: “Summarize risk and affected components for PR-123, and list required checks.”
3. **Retrieval**: fetch PR diff, linked tickets, and recent test results (logged as sources).
4. **Tooling**: run lightweight static checks or dependency diff summaries (logged with inputs/outputs).
5. **Draft answer**: produce a concise risk summary and checklist.
6. **Policy evaluation**: apply safety/completeness rules; flag gaps if evidence is insufficient.
7. **Evidence pack**: display the bundle (sources, tool traces, policy verdicts).
8. **Acceptance criteria**: human reviewer confirms traceability and clarity.

## Success criteria
- Evidence pack is complete and human-verifiable.
- No sensitive data leaves the environment.
- Reviewer can reproduce the response using the recorded trace.
