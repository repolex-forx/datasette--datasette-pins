# Repolex Knowledge Graph of datasette/datasette-pins

RDF knowledge graph data for [datasette/datasette-pins](https://github.com/datasette/datasette-pins), parsed by [repolex](https://repolex.ai).

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
rlex download datasette/datasette-pins
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── d865b27098b525ab6f39e8799abdb168428d7ae2
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── d865b27098b525ab6f39e8799abdb168428d7ae2
│           └── chunk-001.nq.gz
├── blob
│   ├── 011a824d90fe1158d80d286b38dda9688aa2b7c9.nq.gz
│   ├── 085dc3dc51bdd92df80746f80e1e7a88d309540e.nq.gz
│   ├── 0e8cee6b19544b04784ff39530fd7441dadc3277.nq.gz
│   ├── 1003626b34059a91b036d392eda892bef2ae1272.nq.gz
│   ├── 261eeb9e9f8b2b4b0d119366dda99c6fd7d35c64.nq.gz
│   ├── 437073749a8f8efcf06bf6593a52e6ede4a44f30.nq.gz
│   ├── 4670f172539a3bc84e4d2995b1b834cc1e617e54.nq.gz
│   ├── 4743b6ff8aa516448d8ab53225894a8dacb1d1fc.nq.gz
│   ├── 4c09bfcdb03f189d745797b783e2c391b06022be.nq.gz
│   ├── 53b9333dcbbd8356535f6b6e75bc35e02d8b79ad.nq.gz
│   ├── 5e6bf59f5a20ffbc2e0370b2f3d77d1e56c3c9f3.nq.gz
│   ├── 6619b9a3934a6b51770286db198386c605c25e40.nq.gz
│   ├── 7709f63bf1532c133fa4229c0e57b162d2e230ef.nq.gz
│   ├── 9b1ce484017e8ebf6f720a66022893bd3768d6f4.nq.gz
│   ├── b468a87e1138cc8086edaef343f63d7c27f7e8cf.nq.gz
│   ├── cc496b7ea14de9484cc3496542cfa3fd54831513.nq.gz
│   ├── cecec339c9248e0c7048bed046ec1358f638067d.nq.gz
│   ├── d35c7c1765e447891a95c18bddf171da6ad6e8f8.nq.gz
│   ├── d7f1525c069cee10ecf4b110361a434a3724edfe.nq.gz
│   └── fb7ee9cf5ff86e345235e2a410d8543f9d9461f5.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── d865b27098b525ab6f39e8799abdb168428d7ae2.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 28 files
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

[datasette/datasette-pins](https://github.com/datasette/datasette-pins)

---
*Parsed on 2026-10-12 by [repolex](https://repolex.ai)*
