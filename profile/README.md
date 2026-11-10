# GainRatio Open Source

I build open-source software for decisions where "trust me" isn't good enough — the software
has to show its work. The computation runs **on your own device, in your browser**; your private
data doesn't leave it, and results can carry a tamper-evident digital receipt anyone can check later.
Everything below is **100% free to use and live today**, and all published source is open under the MIT license.

- **Open-source hub:** [open-source.gainratio.com](https://open-source.gainratio.com/)
- **Advisory & architecture:** [gainratio.com](https://gainratio.com/)
- **GitHub organization:** [github.com/gainratio](https://github.com/gainratio)

## Why

Software increasingly makes calls that affect real people: whether a payment looks suspicious,
what your private text reveals, or what products you're shown next. Most of it runs on someone else's
server, where you can't see the data it used or check the answer it gave. Those decisions should
be **inspectable** (the code is open), **private** (your data stays with you), and **repeatable**
(the same input produces the exact same answer every time). Each project here moves the work onto
your device and makes the result something you can verify yourself — not something you take on faith.

## Live browser applications (100% free, no account needed, runs on your device)

| Product | What it does | Try it live | Source |
|---|---|---|---|
| **EdgeReco** | Instant search and "you might also like" recommendations across 100,000 products right inside your browser tab (~30 milliseconds per search, with zero search queries sent to a server). | [edge-reco.com](https://edge-reco.com/) · [On-Device Search](https://edge-reco.com/on-device-search) | [gainratio/edge-reco](https://github.com/gainratio/edge-reco) |
| **AlmaMesh** | 100% free Vedic birth-chart (Janam Kundali) and compatibility calculator in **4 languages (English, Hindi, Spanish, and Portuguese)** — running a full planetary astronomy engine directly in your browser so your birth details never leave your device. | [almamesh.com](https://almamesh.com/) · [Free Kundli](https://almamesh.com/free-kundli) · [हिन्दी कुंडली](https://almamesh.com/hi/free-kundli/) · [Kundli Matching](https://almamesh.com/kundli-matching) | [gainratio/almamesh](https://github.com/gainratio/almamesh) |
| **AML-Filter** | Screens names against 31,566 official government sanctions entries (United States, United Nations, European Union, and United Kingdom watchlists) entirely inside your browser tab, explaining why every match scored the way it did. | [aml-filter.com](https://aml-filter.com/) · [Screen a Name](https://aml-filter.com/screen) · [Trust & Verification](https://aml-filter.com/trust/) | [gainratio/aml-filter](https://github.com/gainratio/aml-filter) |

### AI coding & workflow tools

| Project | What it does | Docs / Site | Source |
|---|---|---|---|
| **Agentic Tab Context** | Lets AI coding assistants (Claude Code, Codex, Gemini, Cursor) read and interact with the browser tab you already have open — only after you approve that specific tab — instead of opening a blank logged-out browser. | [open-source.gainratio.com/agentic-tab-context](https://open-source.gainratio.com/agentic-tab-context/) | [gainratio/agentic-tab-context](https://github.com/gainratio/agentic-tab-context) |
| **Agentic Saga** | Runs multi-step Python AI workflows where if step 4 fails, steps 3, 2, and 1 are automatically undone in reverse order so half-finished changes never linger. | [open-source.gainratio.com/agentic-saga](https://open-source.gainratio.com/agentic-saga/) | [gainratio/agentic-saga](https://github.com/gainratio/agentic-saga) |
| **Agentic Context Service** | Shared search and memory service for team AI workflows that enforces who is allowed to read each document and keeps indexes updated as source records change. | [open-source.gainratio.com/agentic-context-service](https://open-source.gainratio.com/agentic-context-service/) | [gainratio/agentic-context-service](https://github.com/gainratio/agentic-context-service) |

### Published code libraries (`npm` & `PyPI`)

| Package | What it does | Get it |
|---|---|---|
| `@gainratio/browser` (TypeScript) | Downloads signed data bundles in a background browser thread, verifies nobody tampered with or rolled them back, and stores them locally for offline search. | [browser.gainratio.com](https://browser.gainratio.com/) · [npm](https://www.npmjs.com/package/@gainratio/browser) · [GitHub](https://github.com/gainratio/edgeproc-browser) |
| `edge-proc` (Python) | Packages datasets or databases into signed, chunked bundles so apps only download the pieces that changed between versions, and searches them offline. | [open-source.gainratio.com/edge-proc](https://open-source.gainratio.com/edge-proc/) · [PyPI](https://pypi.org/project/edge-proc/) · [GitHub](https://github.com/gainratio/edge-proc) |
| `edgeproc-core` (Python) | Splits search indexes cleanly across multiple workspaces or customers and defines the shared error codes used across the search libraries. | [open-source.gainratio.com/edgeproc-core](https://open-source.gainratio.com/edgeproc-core/) · [PyPI](https://pypi.org/project/edgeproc-core/) · [GitHub](https://github.com/gainratio/edgeproc-core) |
| `avow` / `@gainratio/avow` (Python & TypeScript) | Turns any JSON record into a signed digital receipt that anyone can verify offline using only a public key, with identical output in Python and TypeScript. | [avow.gainratio.com](https://avow.gainratio.com/) · [PyPI](https://pypi.org/project/avow/) · [npm](https://www.npmjs.com/package/@gainratio/avow) · [GitHub](https://github.com/gainratio/avow) |
| `@gainratio/privacy-core` (TypeScript) | Swaps credit card numbers, emails, and IDs for safe placeholders on your device before text is sent to an AI model, then puts the real values back into the reply locally. | [privacy.gainratio.com](https://privacy.gainratio.com/) · [npm](https://www.npmjs.com/package/@gainratio/privacy-core) · [GitHub](https://github.com/gainratio/privacy-core) |
| `@gainratio/errors` (TypeScript & Python) | Shared catalog of structured, machine-readable error responses with translated user messages in English, Spanish, Portuguese, and Hindi. | [open-source.gainratio.com/errors](https://open-source.gainratio.com/errors/) · [npm](https://www.npmjs.com/package/@gainratio/errors) · [GitHub](https://github.com/gainratio/errors) |
| `assay-engine` / `@gainratio/assay` | Repeatable offline grading and multi-signal scoring library that explains exactly how every search or ranking score was earned. | [open-source.gainratio.com/assay](https://open-source.gainratio.com/assay/) · [PyPI](https://pypi.org/project/assay-engine/) · [GitHub](https://github.com/gainratio/assay) |

---

### Under the hood (source)

For engineers inspecting the technical stack underneath the plain-English summaries above:

- **Browser execution & storage (`@gainratio/browser`, `EdgeReco`, `AML-Filter`, `AlmaMesh`):** SQLite compiled to WebAssembly (`WASM`) persisted in the browser's Origin Private File System (`OPFS`), hybrid keyword (`FTS5` `BM25`) + 2-bit `TurboQuant` quantized vector retrieval fused via Reciprocal Rank Fusion (`RRF`), and `AlmaMesh`'s Python + `Skyfield` astronomy engine running client-side via `Pyodide` against NASA Jet Propulsion Laboratory `DE421` planetary ephemeris tables.
- **Cryptographic bundles & receipts (`edge-proc`, `avow`):** `Ed25519` public-key signatures, `SHA-256` content addressing over `FastCDC` (content-defined chunking for byte-level delta sync), and `RFC 8785` JSON Canonicalization Scheme (`JCS`) for byte-identical cross-language signing.
- **Governance, policy & structured errors (`agentic-context-service`, `agentic-saga`, `@gainratio/errors`):** Open Policy Agent (`OPA`) access evaluation, Change Data Capture (`CDC`) index synchronization, last-in-first-out (`LIFO`) saga compensation, and `RFC 9457` Problem Details payloads.
- **Organization & CI ([gainratio](https://github.com/gainratio)):** All public source repositories, shared SHA-pinned GitHub Actions and Dagger quality gates ([gainratio/ci](https://github.com/gainratio/ci)), and OIDC trusted-publisher release workflows.

## How I build

- **Runs in your browser.** The core computation happens on your device; your private inputs stay with you.
- **Repeatable.** Same input, same answer, every time — no hidden randomness in the core engines.
- **Verifiable.** Data ships signed and is checked before use; results can carry signed receipts that can be audited later, offline.
- **Honest about limits.** Every project states what it can't promise as plainly as what it can.
- **Tested before shipped.** Behavior is pinned by automated tests that run on every change, including cross-language compatibility suites.
- **Reproducible from clone.** Each repo has a quickstart that takes you from `git clone` to working output.

## About

Harish Seshadri — Senior Principal Engineer (AI/ML) at Gap Inc. This is my open-source
work, built in public. Reach me here on GitHub, or through any of the sites above.

---

All source repositories and packages linked above are MIT-licensed. The products are 100% free,
need no account, and ship with zero analytics SDKs or ad trackers in app source.
