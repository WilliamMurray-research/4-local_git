Local Git: A Deterministic, Provenance‑Aware Version‑Control System for Scientific Research Workflows

Abstract
Local Git is a minimal, provenance‑focused version‑control system designed for scientific and computational research environments where reproducibility, metadata integrity, and deterministic commit structures are more important than distributed collaboration. Implemented as a hybrid Python/Rust system, Local Git provides a stripped‑down CLI, structured metadata schemas, and a memory‑safe commit‑graph engine. This whitepaper presents the system architecture, design principles, metadata model, provenance mechanisms, and workflow semantics that define Local Git as a research‑first alternative to traditional distributed VCS tools.

---

1. Introduction
Scientific research pipelines require version‑control systems that prioritise determinism, provenance, and metadata‑rich commit histories. Traditional distributed VCS tools (e.g., Git) optimise for collaboration, branching, merging, and remote synchronization. These features introduce nondeterministic commit graphs, complex histories, and metadata structures that are poorly suited to reproducible scientific workflows.

Local Git addresses this gap by providing a local‑only, minimal, and governed version‑control system designed specifically for research environments. As stated in the project description:

> “A minimal, research‑focused, version‑controlled CLI built in Python and Rust, designed for structured scientific workflows, provenance tracking, and metadata‑rich commit histories.”

Local Git removes non‑essential Git features and replaces them with deterministic commit semantics, structured metadata validation, and provenance‑aware lineage tracking.

---

2. Motivation
Research artefacts differ fundamentally from software artefacts. They include:

- datasets  
- experiment outputs  
- parameter configurations  
- environment fingerprints  
- symbolic artefacts  
- computational results  

These artefacts require semantic metadata, provenance lineage, and deterministic replayability.

The attached document states:

> “Metadata and provenance must be tightly controlled, and workflows benefit from deterministic, inspectable commit structures.”

Local Git is designed to satisfy these constraints by:

- enforcing deterministic commit graphs  
- validating metadata schemas  
- storing provenance explicitly  
- enabling experiment replay  
- supporting structured diffs of scientific artefacts  

---

3. System Overview
Local Git consists of three primary layers:

3.1 CLI Layer (Python)
Implements:

- command parsing  
- metadata schema validation  
- workflow scripting  
- user‑facing operations  

Python is chosen for its flexibility and ease of integration with research pipelines.

3.2 Provenance Engine (Rust)
Implements:

- commit graph storage  
- hashing  
- metadata serialization  
- memory‑safe operations  

Rust ensures deterministic, safe, and high‑performance commit‑graph manipulation.

3.3 Research Workspace
Contains:

- files  
- datasets  
- experiment outputs  
- symbolic artefacts  

This workspace is the governed substrate for scientific version control.

---

4. Architecture
`
+--------------------------------------------------------+
|                        CLI Layer                       |
|                     Python (Typer)                     |
+---------------------------+----------------------------+
                            | Metadata & Commands
                            v
+--------------------------------------------------------+
|                   Provenance Engine                    |
|         Rust (Hashing, Commit Graph, Storage)          |
+---------------------------+----------------------------+
                            | Structured Artifacts
                            v
+--------------------------------------------------------+
|                     Research Workspace                 |
|            Files, Datasets, Experiment Outputs         |
+--------------------------------------------------------+
`

This architecture is explicitly described in the attached document:

> “Python handles CLI, metadata schemas, and workflow scripting. Rust provides fast, memory‑safe storage, hashing, and commit‑graph operations.”

---

5. Core Features

5.1 Local‑Only Version Control
Local Git removes:

- remotes  
- merges  
- distributed coordination  
- branching complexity  

This ensures deterministic commit graphs and reproducible research histories.

5.2 Structured Metadata
Each commit includes a validated metadata block containing:

- experiment parameters  
- dataset versions  
- environment fingerprints  
- semantic tags  
- provenance parent  

As stated:

> “Metadata is validated and stored in a deterministic format.”

5.3 Provenance Tracking
Commit ancestry forms a research lineage, enabling:

- experiment replay  
- parameter comparison  
- reproducibility audits  
- structured diffs  

This is essential for scientific workflows.

5.4 Hybrid Python/Rust Architecture
Python provides flexibility; Rust provides safety and performance.

---

6. Metadata Schema

Local Git enforces a deterministic metadata schema:

| Field | Description |
|-------|-------------|
| experiment_id | Unique identifier for the experiment |
| parameters | Structured parameter dictionary |
| dataset_version | Versioned dataset reference |
| environment | Environment fingerprint (OS, libs, hardware) |
| semantic_tags | Tags describing experiment semantics |
| provenance_parent | Hash of parent commit |

The attached document states:

> “Metadata fields include: experimentid, parameters, datasetversion, environment, semantictags, provenanceparent.”

Metadata is validated at commit time.

---

7. Commit Graph Design

Local Git uses a linear, deterministic commit graph:

- no merges  
- no branching  
- no remote divergence  
- no nondeterministic histories  

Each commit has exactly one parent, forming a reproducible lineage.

Rust ensures:

- memory‑safe graph operations  
- deterministic hashing  
- stable serialization  

---

8. Workflow Semantics

8.1 Initialization
Creates:

- deterministic commit graph  
- metadata schema  
- workspace manifest  

8.2 Staging
Artifacts are staged with semantic tags.

8.3 Commit
Commit includes:

- structured metadata  
- provenance parent  
- deterministic hash  

8.4 Inspection
Users can inspect:

- lineage  
- metadata diffs  
- reproducibility paths  

8.5 Replay
Deterministic metadata enables exact reconstruction of prior runs.

---

9. Design Principles

| Principle | Meaning |
|----------|---------|
| Determinism | Every commit is reproducible |
| Minimalism | Only essential VCS primitives |
| Transparency | Metadata is explicit and human‑readable |
| Safety | Rust ensures memory‑safe operations |
| Research‑First | Designed for scientific workflows |

These principles are directly stated:

> “Determinism — Every commit is reproducible. Minimalism — Only essential version‑control primitives. Transparency — Metadata is explicit and human‑readable. Safety — Rust ensures memory‑safe commit graph operations. Research‑First — Designed for scientific workflows.”

---

10. Applications

Local Git is ideal for:

- computational experiments  
- scientific notebooks  
- dataset evolution tracking  
- symbolic reasoning pipelines  
- reproducible research workflows  
- provenance‑aware modelling  
- deterministic simulation pipelines  

---

11. Conclusion

Local Git provides a governed, deterministic, metadata‑rich version‑control system tailored for scientific research. By combining Python’s flexibility with Rust’s safety and performance, Local Git offers a reproducible, provenance‑aware alternative to traditional distributed VCS tools. Its structured metadata, deterministic commit graphs, and research‑first design principles make it a foundational component of long‑arc scientific workflows.

---

