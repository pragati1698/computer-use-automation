# Evidence status — honest provenance

## Executed here

- `unit-tests.txt`: 18 passing contract, policy and replay-logic tests; 8 browser cases deselected explicitly.
- Syntax compilation and lint checks passed.
- Replay-logic tests use a test double. They do not constitute live UI evidence.

## Blocked here

- Chromium downloaded, but launch failed because this hosted runtime rejects its socket operation (`process_singleton_posix.cc: socket() failed: Operation not permitted`). Therefore real-browser replay and same-session takeover are implemented but NOT verified here. Run the complete test suite on a normal desktop or the included GitHub Actions workflow.
- No `OPENAI_API_KEY` was present. No genuine LLM discovery was executed, and no discovery logs have been fabricated.

## Before submission

1. Run all tests: `python -m pytest -q` (26 cases, including 8 browser cases).
2. Start the demo and run the README's genuine discovery command. Save `artifacts/discovered.json` and `evidence/live-discovery/events.jsonl`.
3. Replay that discovered artifact for member 67890 and 00000; retain logs in `live-replay/` and `live-not-found/`.
4. Demonstrate human control with the README's interactive command and retain the sanitized handoff log; optionally record the fictional-data browser window.
5. Review all evidence for privacy. The included fixture in `artifacts/fixture.json` must remain clearly labeled; do not relabel it as live discovery.

This folder intentionally contains no fabricated successful browser or model runs.
