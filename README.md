# Repolex Knowledge Graph of beeware/mobile-wheels

RDF knowledge graph data for [beeware/mobile-wheels](https://github.com/beeware/mobile-wheels), parsed by [repolex](https://repolex.ai).

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
rlex download beeware/mobile-wheels
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── c4027f3f258fc0abdf372fc8bfe9b475f462a29d
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── c4027f3f258fc0abdf372fc8bfe9b475f462a29d
│           └── chunk-001.nq.gz
├── blob
│   ├── 04d46493e2b75b6a8d48c5d985403fc69dcd3270.nq.gz
│   ├── 18bc709b273549597ad6de97e6dd31f418b06c6a.nq.gz
│   ├── 1e87566098f7e81c8379e743759e7b16ccdb942d.nq.gz
│   ├── 52a3dce9686f522b1f32f493977987b2ad1f7e0b.nq.gz
│   ├── 5ece16690c55723295c13e490f4072af68abf112.nq.gz
│   ├── 6821bb825bdea08fa29548567423a7f3badcd1ea.nq.gz
│   ├── 758d09f32a990bb5b98efc5cb06ee3a5d13fd834.nq.gz
│   ├── 953c60a7fb05561e6dc25ad9885cb295e2663f62.nq.gz
│   ├── 96fbd9a307c44200b5d394084a9c041480842f28.nq.gz
│   ├── a756d0c7720c1a07ea2bec6189523be0cc59c712.nq.gz
│   ├── aa61fc3cedb800ef6dce2953cb78fc80561f51f9.nq.gz
│   ├── b0c53c7c5c60ce8c9262ed8cc4de5c132461aba2.nq.gz
│   ├── b3ac5cd370f7e4305da6efaed619ec0c0980d70a.nq.gz
│   ├── c4d88e8173e484996f9c1fe716bd0fb7e4c8a73b.nq.gz
│   ├── cb311ba160a3f717b12cd2025de87fb4683c41a0.nq.gz
│   ├── d19833248e78114677866410ead78b271740e191.nq.gz
│   ├── e803ae04267afa58f25ccf07639fb096d8a9c0c7.nq.gz
│   └── ea71977788719f0ee3df199ce1f99e6dab3bc3ac.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── c4027f3f258fc0abdf372fc8bfe9b475f462a29d.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 26 files
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

[beeware/mobile-wheels](https://github.com/beeware/mobile-wheels)

---
*Parsed on 2026-11-07 by [repolex](https://repolex.ai)*
