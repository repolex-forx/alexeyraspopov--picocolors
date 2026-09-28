# Repolex Knowledge Graph of alexeyraspopov/picocolors

RDF knowledge graph data for [alexeyraspopov/picocolors](https://github.com/alexeyraspopov/picocolors), parsed by [repolex](https://repolex.ai).

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
rlex download alexeyraspopov/picocolors
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 7249f8c5d4825550f70bc1ea98652639933d3bbd
│   │       └── chunk-001.nq.gz
│   ├── lsp
│   │   └── 7249f8c5d4825550f70bc1ea98652639933d3bbd.nq.gz
│   └── repolex
│       └── 7249f8c5d4825550f70bc1ea98652639933d3bbd
│           └── chunk-001.nq.gz
├── blob
│   ├── 140f7177a376d9e30328006c7826af91857df933.nq.gz
│   ├── 19bfc71365ef998a07af12eee21549620b27c6a6.nq.gz
│   ├── 1f10a24ad46853b6314b87a00a92e697b1010133.nq.gz
│   ├── 37ad6ac0fff8c0152250958b0e8960a41b4195c2.nq.gz
│   ├── 3c3629e647f5ddf82548912e337bea9826b434af.nq.gz
│   ├── 46c9b95d4b83c8eba2d9ed406f49930a9fdaf3e3.nq.gz
│   ├── 4bc5da39a9dc7abc4727fc0bac25e0dcdc4b365e.nq.gz
│   ├── 537cdb9c7d97649af1d016714e83ae8af9a686d9.nq.gz
│   ├── 54e3aa3b2f82966cc83479883b9979aa794ce59a.nq.gz
│   ├── 58a1488954dd1aedd9806f52399dcec55aff17cd.nq.gz
│   ├── 6179ed893acce5e4ebc9b4793c2f34a4cea92790.nq.gz
│   ├── 80e207d57934c2d752f40206e6cdf98401aa8383.nq.gz
│   ├── 94e146a82221e527be835656549ddfb1b41fd0c9.nq.gz
│   ├── 9ca90e86442bffa7467ca141dedef5e408b55d89.nq.gz
│   ├── 9dcf637cda1ae2b7ed3281c42463da234ae91398.nq.gz
│   ├── c96d5962fd90fbeee64da7f69e9ec8bdd226988b.nq.gz
│   ├── cd1aec46792f4bdb4fd06aeabf1fd93c8b3f11ea.nq.gz
│   ├── e32df8548820fdf608b39331be07a8519a1b6c46.nq.gz
│   └── ee119bc71ccc70dc7cf7d2e02d0816f18038179b.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── dep
│   └── 7249f8c5d4825550f70bc1ea98652639933d3bbd.nq.gz
├── filetree
│   └── 7249f8c5d4825550f70bc1ea98652639933d3bbd.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

15 directories, 29 files
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

[alexeyraspopov/picocolors](https://github.com/alexeyraspopov/picocolors)

---
*Parsed on 2026-09-28 by [repolex](https://repolex.ai)*
