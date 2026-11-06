# Repolex Knowledge Graph of sphinx-contrib/domaintools

RDF knowledge graph data for [sphinx-contrib/domaintools](https://github.com/sphinx-contrib/domaintools), parsed by [repolex](https://repolex.ai).

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
rlex download sphinx-contrib/domaintools
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── cc6a5dcb3204325f52d160a0da7e097f3a825c8c
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── cc6a5dcb3204325f52d160a0da7e097f3a825c8c
│           └── chunk-001.nq.gz
├── blob
│   ├── 3dd5e60b62329f21d14b10b71b8fbe6a2a3e69f9.nq.gz
│   ├── 8e7e2bc0d26ebc39199523caf9850ff62f3d650a.nq.gz
│   ├── 926cc7b14c1ecdca8d3c7ae299350d98a3f9c905.nq.gz
│   ├── 9caa7a3d7d0bd2d015d173d52af41462a7bcd8db.nq.gz
│   ├── a3d82f83d34c6fa9bb9bfbb10f9ada8621e3c307.nq.gz
│   ├── b5a7dc29ef0f7f3593b1c61cfc5dfe8a17d3918c.nq.gz
│   ├── bfb9f4b5e992f8af7ca8153e93dab5c67e47976f.nq.gz
│   ├── cfba05124027a32b886f222fdbe2fd53867e8010.nq.gz
│   ├── f06b4f92fd63e634fbe8ee26ed5f7ba110bbdbc6.nq.gz
│   └── f39ed277df32dedf036872baddf08684078b4adf.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── cc6a5dcb3204325f52d160a0da7e097f3a825c8c.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 18 files
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

[sphinx-contrib/domaintools](https://github.com/sphinx-contrib/domaintools)

---
*Parsed on 2026-11-06 by [repolex](https://repolex.ai)*
