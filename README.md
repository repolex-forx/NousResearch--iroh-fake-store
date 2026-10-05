# Repolex Knowledge Graph of NousResearch/iroh-fake-store

RDF knowledge graph data for [NousResearch/iroh-fake-store](https://github.com/NousResearch/iroh-fake-store), parsed by [repolex](https://repolex.ai).

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
rlex download NousResearch/iroh-fake-store
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── b06cf0135dd65de3336815eaf4dc4a6ba552b3b1
│   │       └── chunk-001.nq.gz
│   ├── lsp
│   │   └── b06cf0135dd65de3336815eaf4dc4a6ba552b3b1.nq.gz
│   └── repolex
│       └── b06cf0135dd65de3336815eaf4dc4a6ba552b3b1
│           └── chunk-001.nq.gz
├── blob
│   ├── 022d05e23b969d7a360f3f2737693d79a176960b.nq.gz
│   ├── 273b10ad25034a83c25cf5363b1a0596145d4904.nq.gz
│   ├── 3550a30f2de389e537ee40ca5e64a77dc185c79b.nq.gz
│   ├── 5bde95386f7d12a488ba664d33b140ab7f27ac4c.nq.gz
│   ├── cc4f19e5210ea0db7f059be51788f8a2ac2c7175.nq.gz
│   ├── d0a39bb3513549fcb6eac0f96d0fa6971e9b6394.nq.gz
│   ├── dcce183ed636aebad267e86985631fdbc1f486e5.nq.gz
│   └── edb874dd1d59dc3d61d11d1cf78bc901a64d9225.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── dep
│   └── b06cf0135dd65de3336815eaf4dc4a6ba552b3b1.nq.gz
├── filetree
│   └── b06cf0135dd65de3336815eaf4dc4a6ba552b3b1.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

14 directories, 17 files
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

[NousResearch/iroh-fake-store](https://github.com/NousResearch/iroh-fake-store)

---
*Parsed on 2026-10-05 by [repolex](https://repolex.ai)*
