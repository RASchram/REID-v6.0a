# REID v6.0a — Canonical Architecture Release

REID v6.0a is the next major evolution of the Relational Emergent Identity Dynamics architecture. It consolidates the lineage from earlier versions into a unified four-layer cognitive spine with expanded invariants, refined requirements governance, and an enterprise-ready integration surface.

This repository contains the public-safe v6.0a artifacts. Substrate mechanics, identity-lock internals, and build sequencing remain private.


## Purpose

This repository provides the public architectural surface of REID v6.0a. It is designed to support technical reviewers, enterprise architects, and systems engineers who require a clear understanding of the structural model without exposure to identity-locked or substrate-level components.

The repository maintains lineage continuity, demonstrates architectural evolution, and provides stable, versioned artifacts suitable for public reference.


## Included Artifacts (Public-Safe Subset)

### Architecture
- Four-Layer Spine Overview (A-09)
- Requirements Architecture (A-12)
- Enterprise Integration Overview (A-13)
- Cross-Layer Binding Rules (Overview)

### Definitions and Invariants
- Core Definitions and Invariants (v5.0a)
- UCSM Primitives Overview

### Lineage
- Version Lineage and Continuity Record (v5.0a)

### Requirements
- Traceability Matrix Standard (R-20)
- Requirements Lifecycle Governance (Overview)

### Dependency Schema
- Dependency Graph Schema (DGS-0002-v2.0)
- Dependency Graph Notes


## Architectural Position

REID v6.0a introduces a unified four-layer architecture spine, a stable requirements architecture with lifecycle governance, expanded core definitions and invariants, and a consistent cross-layer binding model. It aligns with the REID dependency and traceability schema and provides an enterprise-grade integration surface.

These materials represent the public-safe architectural boundary of the v6.0a build suite.


## Excluded Materials

This repository intentionally excludes all identity-locked or substrate-level artifacts, including:

- Meta-Substrate mechanics
- Mode engines
- Closure and Immunity Systems
- Orchestration Spine internals
- Build sequencing or manifest logic
- Identity-Lock parameters
- Any of the private 46-artifact build suite

These components remain private and governed by REID Identity-Lock rules.


## Lineage

REID v6.0a succeeds:
- REID v5.0a (Core Architecture and Invariants)
- REID v3.1.1a (Unified Specification Corpus)

The v3.1.1a repository is preserved as a deprecated historical baseline.


## Repository Structure

REID-v6.0a/
│
├── README.md
├── CHANGELOG.md
├── LICENSE
│
├── docs/
│   ├── architecture/
│   ├── definitions/
│   ├── lineage/
│   ├── requirements/
│   ├── dependency/
│   └── integration/
│
└── assets/
    ├── diagrams/
    ├── images/
    └── logos/


## License

This repository contains public-safe documentation only. All private REID artifacts remain governed by REID Identity-Lock rules.
