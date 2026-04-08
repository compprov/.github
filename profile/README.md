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
- **Manual parallelization** — optimizing for multi-core hardware requires error-prone code refactoring (in progress)

compprov solves all three simultaneously, from a single instrumented execution. 

Because the serialized CPG serves as a self-contained, immutable record of the operational logic at the moment of execution, it eliminates the necessity of reconstructing legacy software states. This ensures that the numerical integrity of historical data remains verifiable even years after the original computational environment has been decommissioned.

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
| [compprov-core](https://github.com/compprov/compprov-core) | [![GitHub release](https://img.shields.io/github/v/release/compprov/compprov-core?color=brightgreen)](https://github.com/compprov/compprov-core/releases) | Context wrapping and CPG construction |
| [compprov-render](https://github.com/compprov/compprov-render) | [![GitHub release](https://img.shields.io/github/v/release/compprov/compprov-render?color=brightgreen)](https://github.com/compprov/compprov-render/releases) | Browser-based graph and plot visualization of CPG data |

## Roadmap

### compprov-core — Automatic parallelization

Analyze the CPG structure to detect independent branches and schedule their execution
concurrently — without requiring any code changes from the developer.
The DAG already captures all data dependencies, making it possible to determine which
operations can safely run in parallel and generate an optimized execution plan automatically.

### compprov-core — JSON snapshot signing via timestamp protocol

The exported CPG JSON snapshot will be signed using a timestamp protocol, producing a
verifiable proof of the snapshot's contents at the moment of export. The signature travels
with the JSON file, making it possible for any recipient to verify that the file has not
been altered since it was produced.

### compprov-analytics — Comparison and backtrace tool

A new module focused on analysis across multiple CPG snapshots:

- **Diff / comparison** — given two or more snapshots, detect and rank the most significant
  numerical and structural differences; highlight which variables and operations diverged and by how much
- **Backtrace** — for any output variable, walk the CPG backwards to identify which inputs
  and operations contributed most to a given result or anomaly
- **Multi-snapshot analysis** — compare a set of runs across different parameter sets or
  time periods to surface patterns and outliers

## License

Apache License 2.0 — Copyright 2026 Minas Abramyan
