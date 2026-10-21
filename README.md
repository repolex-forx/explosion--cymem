# Repolex Knowledge Graph of explosion/cymem

RDF knowledge graph data for [explosion/cymem](https://github.com/explosion/cymem), parsed by [repolex](https://repolex.ai).

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
rlex download explosion/cymem
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── ab7415bc36d77a937bb03392c2a3bd3123d9fd10
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── ab7415bc36d77a937bb03392c2a3bd3123d9fd10
│           └── chunk-001.nq.gz
├── blob
│   ├── 12ccb03c21231f81fd33537d083283a8d6013e32.nq.gz
│   ├── 19c5a93b7636df1e8033f1e316632717047a677f.nq.gz
│   ├── 24441e75ec0e1b098962d4c0603ed61db1b2e537.nq.gz
│   ├── 3eb751176df5d69814ab15c29aa8118e12e02838.nq.gz
│   ├── 44214776e6e0f2fc66d87986d31f118790eb1f35.nq.gz
│   ├── 4ef5c685b566e683a6cdac87195a3963f229943c.nq.gz
│   ├── 5657d3a5d702bfaabe0d90d450ad064ffba8689d.nq.gz
│   ├── 6697e24086837d52b325a4ad5a57ba168ebf0fb3.nq.gz
│   ├── 6997a263fed09a95247cbefd0b245517283ce69d.nq.gz
│   ├── 71050e76b1b0b94ccb3607ca4aabf38c0cebbba5.nq.gz
│   ├── a55014485a1e94a14df8dfaf1bce1c2921d047c3.nq.gz
│   ├── acc29f3937d362b7c7ca16fc445a44f3e3ad964f.nq.gz
│   ├── c5eabd59f2eba4428daeaf8fa39722155812a194.nq.gz
│   ├── dbcbd9504dc5b6a29e9a72c21f1ab3c00366c362.nq.gz
│   ├── ddeb6070a72e208870902b09fd01646a1a6dc3e0.nq.gz
│   └── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── ab7415bc36d77a937bb03392c2a3bd3123d9fd10.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 24 files
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

[explosion/cymem](https://github.com/explosion/cymem)

---
*Parsed on 2026-10-21 by [repolex](https://repolex.ai)*
