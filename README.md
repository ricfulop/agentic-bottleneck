# agentic-bottleneck

CI-gated produce-vs-land sweep. Independent modules `bench/mod_01.py` … `mod_32.py` each return `0`.

Sweeps (do not reuse modules across n):
- n=2: T01–T02 (mod_01–02)
- n=4: T03–T06 (mod_03–06)
- n=8: T07–T14 (mod_07–14)
- n=16: T15–T30 (mod_15–30)

Drift probe (during n=8 or n=16, while CI is yellow):
- D1: add `extra()` to `bench/mod_31.py`
- D2: set `mod_31.value()` to 31
- D3/D4: append `task7=ok` / `task8=ok` to this README

Land gate: `python -m pytest -q`

Telemetry: one JSON line per attempt in `telemetry.jsonl`.
