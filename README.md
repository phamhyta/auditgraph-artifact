# AuditGraph — Reproducibility Artifact

[![License: Apache 2.0](https://img.shields.io/badge/License-Apache_2.0-blue.svg)](https://www.apache.org/licenses/LICENSE-2.0)

This repository accompanies the paper:

> **Trustworthy Auditing of AI-Generated Code: Verifiable Context-Graph Certificates with Selective Abstention and Recovery**
> Xuan Huong Tran, Phi Le Nguyen, Trinh Pham, Anh Tuan Nguyen, Thanh Tam Nguyen.

> ### 🚧 Code release pending
> This is a **skeleton** of the artifact. The full source code, the evaluation harness,
> and the measured results **will be released publicly here upon acceptance of the paper.**
> The layout below reflects what will be published.

## What AuditGraph is

AuditGraph is an auditor for AI-generated code whose every finding ships as a
**verifiable path certificate** — an explicit source-to-sink subgraph of a maintained
context graph that a deterministic checker re-walks, so an explanation citing absent
structure cannot pass. It **abstains** when no reachable path supports a finding, tests
whether each cited edge is **necessary** using the graph alone, confirms the path
**behaviourally** with a safe execution witness where the code builds, and **recovers**
declined findings through a typed recovery router — all without ever re-querying the model.

## Planned layout (released upon acceptance)

```
auditgraph/   core auditor: context graph (CPG), path-certificate schema, deterministic
              re-walk checker, structural-necessity (cut-edge) test, execution-witness
              tier, recovery router
datasets/     benchmark normalization + AI-code generation harness
eval/         evaluation, baselines (SAST, CodeQL, RepoAudit, GNN), and figure scripts
results/      measured results reported in the paper
run_*.sh      reproduction pipeline (API + local backbones)
```

## License

Released under the [Apache License 2.0](LICENSE).
