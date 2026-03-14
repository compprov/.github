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
- **Manual parallelization** — optimizing for multi-core hardware requires error-prone code refactoring

compprov solves all three simultaneously, from a single instrumented execution.

## How it works

Every variable gets a **descriptor** (source, type, unit, unique ID).
Every operation gets a **descriptor** (input IDs, function signature, timestamp).
Together they form the **CPG** — a DAG that serves as:

| Purpose | What the CPG enables |
|---|---|
| Auditing & Debugging | Trace any anomalous result back to the exact input and operation that caused it |
| Context Comparison | Diff two CPGs to highlight structural or numerical divergence between runs |
| Auto-Parallelization | Schedule independent DAG branches for concurrent execution automatically |

## Modules

| Repository | Status | Description |
|---|---|---|
| [compprov-core](https://github.com/compprov/compprov-core) | ✅ First release | Context wrapping, CPG construction, VODL descriptors |
| [compprov-render](https://github.com/compprov/compprov-render) | ✅ First version | Browser-based graph and plot visualization of CPG data |

## License

Apache License 2.0 — Copyright 2026 Minas Abramyan
