# GainRatio Open Source

I build open-source software for decisions where "trust me" isn't good enough — the software
has to show its work. The computation runs **on your own device, in your browser**; data
doesn't leave it, and results can carry a cryptographic receipt anyone can check later.
Everything below is **100% free to use and live today**, and all published source is MIT-licensed.

- **Open-source hub:** [open-source.gainratio.com](https://open-source.gainratio.com/)
- **Advisory & architecture:** [gainratio.com](https://gainratio.com/)
- **GitHub organization:** [github.com/gainratio](https://github.com/gainratio)

## Why

Software increasingly makes calls that affect real people: whether a payment looks suspicious,
what your private text reveals, what you're shown next. Most of it runs on someone else's
server, where you can't see the data it used or check the answer it gave. I think those
decisions should be **inspectable** (the code is open), **private** (your data stays with
you), and **repeatable** (same input, same answer, every time). So each project here moves
the computation into your browser and makes the result something you can verify — not
something you have to take on faith.

## Live browser applications (100% free, zero-account, local-first)

| Product | What it does | Try it live | Source |
|---|---|---|---|
| **EdgeReco** | 100,000-product hybrid vector + BM25 search and "you might also like" recommendations running inside the shopper's browser tab (SQLite WASM + OPFS + 2-bit TurboQuant, ~30ms median latency, zero per-query server calls). | [edge-reco.com](https://edge-reco.com/) · [On-Device Search](https://edge-reco.com/on-device-search) | [gainratio/edge-reco](https://github.com/gainratio/edge-reco) |
| **AlmaMesh** | Free Vedic astrology & Janam Kundali calculator (Lagna, Chandra Rashi, 27 Nakshatras, Vimshottari Dasha, Ashtakoot 36 Gun Milan, Muhurta) running a full astronomy engine (Skyfield / Pyodide + JPL DE421) in your browser. | [almamesh.com](https://almamesh.com/) · [Free Kundli](https://almamesh.com/free-kundli) · [हिन्दी कुंडली](https://almamesh.com/hi/free-kundli/) · [Kundli Matching](https://almamesh.com/kundli-matching) | [gainratio/almamesh](https://github.com/gainratio/almamesh) |
| **AML-Filter** | Sanctions-list screening against 31,566 entities (OFAC SDN, UN, EU, UK OFSI) entirely inside your browser tab: fuzzy name matching over Ed25519-signed watchlists with an explanation for every match. | [aml-filter.com](https://aml-filter.com/) · [Screen a Name](https://aml-filter.com/screen) · [Trust & Verification](https://aml-filter.com/trust/) | [gainratio/aml-filter](https://github.com/gainratio/aml-filter) |

### Agentic developer tools & substrates

| Project | What it does | Docs / Site | Source |
|---|---|---|---|
| **Agentic Tab Context (`atc`)** | Lets AI coding agents (Claude Code, Codex, Gemini, Cursor) inspect and use the browser tab you already have open — with explicit per-tab consent — instead of spawning a fresh logged-out Playwright browser. | [open-source.gainratio.com/agentic-tab-context](https://open-source.gainratio.com/agentic-tab-context/) | [gainratio/agentic-tab-context](https://github.com/gainratio/agentic-tab-context) |
| **Agentic Saga** | Deterministic Saga orchestrator for Python AI agents: run multi-step tool workflows with automatic LIFO compensation and rollback on failure. | [open-source.gainratio.com/agentic-saga](https://open-source.gainratio.com/agentic-saga/) | [gainratio/agentic-saga](https://github.com/gainratio/agentic-saga) |
| **Agentic Context Service** | Governed OpenSearch context and memory hub for agentic workflows with OPA policy enforcement and CDC sync. | [open-source.gainratio.com/agentic-context-service](https://open-source.gainratio.com/agentic-context-service/) | [gainratio/agentic-context-service](https://github.com/gainratio/agentic-context-service) |

### Published packages (`npm` & `PyPI`)

| Package | What it does | Get it |
|---|---|---|
| `@gainratio/browser` (TypeScript) | Verifies and syncs `edge-proc` bundles in a browser Web Worker, with OPFS SQLite FTS5 BM25, JSON1, and 2-bit TurboQuant vector search. | [browser.gainratio.com](https://browser.gainratio.com/) · [npm](https://www.npmjs.com/package/@gainratio/browser) · [GitHub](https://github.com/gainratio/edgeproc-browser) |
| `edge-proc` (Python) | Publishes data or `.sqlite` databases as Ed25519-signed, content-addressed bundles with FastCDC delta sync and searches them offline. | [open-source.gainratio.com/edge-proc](https://open-source.gainratio.com/edge-proc/) · [PyPI](https://pypi.org/project/edge-proc/) · [GitHub](https://github.com/gainratio/edge-proc) |
| `edgeproc-core` (Python) | Multi-tenant vector-index partitioning protocol and canonical error catalog underneath `edge-proc` and `EdgeReco`. | [open-source.gainratio.com/edgeproc-core](https://open-source.gainratio.com/edgeproc-core/) · [PyPI](https://pypi.org/project/edgeproc-core/) · [GitHub](https://github.com/gainratio/edgeproc-core) |
| `avow` / `@gainratio/avow` (Python & TS) | Signed, offline-verifiable receipts (Ed25519 over RFC 8785 JCS): wrap a result in an envelope anyone can later verify using only a public key. | [avow.gainratio.com](https://avow.gainratio.com/) · [PyPI](https://pypi.org/project/avow/) · [npm](https://www.npmjs.com/package/@gainratio/avow) · [GitHub](https://github.com/gainratio/avow) |
| `@gainratio/privacy-core` (TypeScript) | Redacts private text on your device before it reaches an AI model, then restores the real values locally in the reply — sending raw text is a compile error, not a policy. | [privacy.gainratio.com](https://privacy.gainratio.com/) · [npm](https://www.npmjs.com/package/@gainratio/privacy-core) · [GitHub](https://github.com/gainratio/privacy-core) |
| `@gainratio/errors` (TypeScript & Python) | Typed error registry with RFC 9457 Problem Details and i18n, matching `edgeproc-core` error codes. | [open-source.gainratio.com/errors](https://open-source.gainratio.com/errors/) · [npm](https://www.npmjs.com/package/@gainratio/errors) · [GitHub](https://github.com/gainratio/errors) |
| `assay-engine` / `@gainratio/assay` | Deterministic offline evaluation harness and calibrated multi-metric scoring engine for ranking and retrieval quality gates. | [open-source.gainratio.com/assay](https://open-source.gainratio.com/assay/) · [PyPI](https://pypi.org/project/assay-engine/) · [GitHub](https://github.com/gainratio/assay) |

### Under the hood (source)

- [gainratio](https://github.com/gainratio) — the organization hosting all public source repositories, shared Dagger CI modules ([gainratio/ci](https://github.com/gainratio/ci)), and release workflows.

## How I build

- **Runs in your browser.** The interesting computation happens on your device; your data doesn't leave it.
- **Deterministic.** Same input, same answer, every time — no hidden randomness in the core engines.
- **Verifiable.** Data ships signed and is checked before use; results can carry signed receipts that can be audited later, offline.
- **Honest about limits.** Every project states what it can't promise as plainly as what it can.
- **Tested before shipped.** Behavior is pinned by automated tests that run on every change, including cross-language compatibility suites.
- **Reproducible from clone.** Each repo has a quickstart that takes you from `git clone` to working output.

## About

Harish Seshadri — Senior Principal Engineer (AI/ML) at Gap Inc. This is my open-source
work, built in public. Reach me here on GitHub, or through any of the sites above.

---

All source repositories and packages linked above are MIT-licensed. The products are free,
need no account, and their pages load no third-party tracking scripts.
