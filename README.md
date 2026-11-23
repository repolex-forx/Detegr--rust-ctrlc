# Repolex Knowledge Graph of Detegr/rust-ctrlc

RDF knowledge graph data for [Detegr/rust-ctrlc](https://github.com/Detegr/rust-ctrlc), parsed by [repolex](https://repolex.ai).

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
rlex download Detegr/rust-ctrlc
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── f9de9565ad29d91c567071f9ed8018113227d12a
│   │       └── chunk-001.nq.gz
│   ├── lsp
│   │   └── f9de9565ad29d91c567071f9ed8018113227d12a.nq.gz
│   └── repolex
│       └── f9de9565ad29d91c567071f9ed8018113227d12a
│           └── chunk-001.nq.gz
├── blob
│   ├── 31aa79387f27e730e33d871925e152e35e428031.nq.gz
│   ├── 3519798970a88b25958333ce7e3cb3baf340c239.nq.gz
│   ├── 667557c8be44f396dad9ef98616bc93ba69f1b7a.nq.gz
│   ├── 6cfdd5ebfec2ad6d249295bf155112a321c45536.nq.gz
│   ├── 9557b09c9051382136a9492dd353aedcfe3b729f.nq.gz
│   ├── 9ce9a410206b71a55d41416e8a4ddf058e0e6524.nq.gz
│   ├── a9d37c560c6ab8d4afbf47eda643e8c42e857716.nq.gz
│   ├── b14b26253016393e85c89377b8d214088d2cb389.nq.gz
│   ├── b51c388429216d66675e63b5f81a00c65c3a07b8.nq.gz
│   ├── c59068d75fc9e7fb5829e3f64cbdf1c444f48815.nq.gz
│   ├── cc01b80229b65e6b1273ea65972db6245a70aa36.nq.gz
│   ├── cc9ed3f6ba72054498efc37d06b1aba3e839acab.nq.gz
│   ├── e453637ee2c56089b8962a61553fdf13369cfe81.nq.gz
│   ├── f3b37e958107fd3275c2d745a6e795e9f0a03d16.nq.gz
│   ├── f703c18fd03844ec48a45d8ee86e2ef93edafe0e.nq.gz
│   └── f77fd5c8d8390b234914e0a690dbf8d5e9f4c078.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── dep
│   └── f9de9565ad29d91c567071f9ed8018113227d12a.nq.gz
├── filetree
│   └── f9de9565ad29d91c567071f9ed8018113227d12a.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

15 directories, 26 files
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

[Detegr/rust-ctrlc](https://github.com/Detegr/rust-ctrlc)

---
*Parsed on 2026-11-23 by [repolex](https://repolex.ai)*
