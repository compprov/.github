# compprov — Computational Provenance

**compprov** is an open-source Java framework that automatically creates a structured,
machine-readable **Calculation Provenance Graph (CPG)** for every computation.

It wraps numerical variables and operations into a tracked execution context, forming a
Directed Acyclic Graph (DAG) that captures the complete audit trail of a calculation —
without requiring developers to manually build graphs or restructure existing code.

## Why compprov?

Complex numerical systems in finance, engineering, and scientific computing share three critical problems:

- **Opacity** — a single output with no traceable audit trail makes debugging painful
- **Irreproducibility** — no native mechanism to guarantee a calculation can be precisely reconstructed
- **Software & Codebase Decay** — business logic and software libraries evolve constantly, making legacy calculations nearly impossible to audit years later. Because `CompProv` separates structural lineage from the executable code, it preserves the exact mathematical truth of a calculation in a lightweight Snapshot. For auditing purposes, you don’t need to resurrect dead repositories, dig through obsolete dependencies, or reconstruct broken build environments—as long as the basic wrappers/operation descriptors are provided, the calculation can be analyzed and verified out-of-the-box.

compprov solves all three simultaneously, from a single instrumented execution. 

## How it works

Every variable gets a **descriptor** (source, type, unit, unique ID).
Every operation gets a **descriptor** (input IDs, function signature, timestamp).
Together they form the **CPG** — a DAG that serves as:

| Purpose | What the CPG enables |
|---|---|
| Auditing & Debugging | Trace any anomalous result back to the exact input and operation that caused it |
| Context Comparison | Diff two CPGs to highlight structural or numerical divergence between runs |

## Modules

| Repository | Status | Description |
|---|---|---|
| [compprov-core](https://github.com/compprov/compprov-core) | [![GitHub release](https://img.shields.io/github/v/release/compprov/compprov-core?color=brightgreen)](https://github.com/compprov/compprov-core/releases) | Context wrapping and CPG construction |
| [compprov-trust](https://github.com/compprov/compprov-trust) | [![GitHub release](https://img.shields.io/github/v/release/compprov/compprov-trust?color=brightgreen)](https://github.com/compprov/compprov-trust/releases) | Signature generation and verification module for the CPG |
| [compprov-render](https://github.com/compprov/compprov-render) | [![GitHub release](https://img.shields.io/github/v/release/compprov/compprov-render?color=brightgreen)](https://github.com/compprov/compprov-render/releases) | Browser-based graph and plot visualization of CPG data |
| [compprov-analytics](https://github.com/compprov/compprov-analytics) | [![GitHub release](https://img.shields.io/github/v/release/compprov/compprov-analytics?color=brightgreen)](https://github.com/compprov/compprov-analytics/releases) | CLI tool that audits compprov-core Calculation Provenance Graph snapshots |

## License

Apache License 2.0 — Copyright 2026 Minas Abramyan
[LinkedIn](https://www.linkedin.com/in/mabramyan/)
