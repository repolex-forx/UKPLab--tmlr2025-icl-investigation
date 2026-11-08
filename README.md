# Repolex Knowledge Graph of UKPLab/tmlr2025-icl-investigation

RDF knowledge graph data for [UKPLab/tmlr2025-icl-investigation](https://github.com/UKPLab/tmlr2025-icl-investigation), parsed by [repolex](https://repolex.ai).

> **Note**: This data is experimental and subject to change without notice.

## How to use this data

The easiest way to get started is to install the [rlex](https://github.com/repolex-ai/rlex) query tool:

```bash
cargo install --git https://github.com/repolex-ai/rlex
```

Verify the install:

```bash
rlex --help
```

**rlex is designed to be used primarily by LLMs in a terminal.** Start up your favorite AI assistant and ask it to use rlex. It handles the SPARQL — you just ask questions in plain English.

To load this repo's data:

```bash
rlex download UKPLab/tmlr2025-icl-investigation
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 90668b36a42edc82c7aef326352ac0c87afdb617
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 90668b36a42edc82c7aef326352ac0c87afdb617
│           └── chunk-001.nq.gz
├── blob
│   ├── 074f94b75cc59fd40f884b0044efd14c26280da2.nq.gz
│   ├── 261eeb9e9f8b2b4b0d119366dda99c6fd7d35c64.nq.gz
│   ├── 27999cc19bc397dcaf85ff1171484ce160b03f4c.nq.gz
│   ├── 6b0df7ad87fecc4508aa0ccdeffb563af5f04c29.nq.gz
│   ├── 817ae674bce8f18a221af4de530ec1be39f9fd98.nq.gz
│   ├── 8fc07fcabaca4c1e4cc9636587d4f958330571fc.nq.gz
│   ├── a221e2dcf416b550dbc1d80e28214f33507d959b.nq.gz
│   ├── b3e5bb3d977b939e29a3335e763950e404faca55.nq.gz
│   ├── d29d9e50b9248664bfc5c335dfa36cfe320c657a.nq.gz
│   ├── de4d9d077ce7714a8e98fb1bec9572a62eb1ab0b.nq.gz
│   ├── e63156610286b2fb70694242bf9e3294a52895c3.nq.gz
│   └── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 90668b36a42edc82c7aef326352ac0c87afdb617.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

12 directories, 19 files
```

| Directory | What it contains |
|-----------|-----------------|
| `blob/` | Per-file AST graphs, content-addressed by git blob SHA. Each file in the source repo gets its own graph. |
| `aggregate/ast/` | Combined AST graph per parsed commit. Merges all blob graphs for a snapshot of the entire codebase at that point. |
| `aggregate/lsp/` | Language Server Protocol enrichment: resolved symbols, definitions, references, and type information. |
| `aggregate/dataflow/` | Interprocedural data flow edges between functions and modules. |
| `aggregate/repolex/` | Combined graph (AST + LSP + dataflow) per commit. |
| `commit/` | Git commit metadata (author, date, message, parent links). |
| `branch/` | Branch metadata. |
| `tag/` | Tag metadata. |
| `filetree/` | File tree snapshots per commit (which files existed and their blob SHAs). |
| `audit/` | Code architecture and graph audit reports per commit. |

## Source repository

[UKPLab/tmlr2025-icl-investigation](https://github.com/UKPLab/tmlr2025-icl-investigation)

---
*Parsed on 2026-11-08 by [repolex](https://repolex.ai)*
