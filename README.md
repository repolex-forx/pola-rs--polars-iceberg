# Repolex Knowledge Graph of pola-rs/polars-iceberg

RDF knowledge graph data for [pola-rs/polars-iceberg](https://github.com/pola-rs/polars-iceberg), parsed by [repolex](https://repolex.ai).

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
rlex download pola-rs/polars-iceberg
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 400eab094a98da2ab89d33f36f53b039f73d4db2
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 400eab094a98da2ab89d33f36f53b039f73d4db2
│           └── chunk-001.nq.gz
├── blob
│   ├── 0fb070f36b5d9d82fb288a21d9fe8b47a1fefaaf.nq.gz
│   ├── 106f830393b4b687b5c61f98b9317126ca59e262.nq.gz
│   ├── 1600d418ec24b660ed77eba3c95a21bf22272cfe.nq.gz
│   ├── 1dcc13a0cd38c5c4b8d1b9ab26ba4c66327e1dd4.nq.gz
│   ├── 243c40f2e1da428032625ee96321b5148eb05da0.nq.gz
│   ├── 33b09bbb6c5bd43c5e985e2affed64c5ed093616.nq.gz
│   ├── 503c137f66252b43104d0de81ba24e3952944e9f.nq.gz
│   ├── 5509ddc9a70f855c205aaf0de2b67ffafaa2b52e.nq.gz
│   ├── 583dbd010dc30c08a4def8f56d129ac4fe96fb3d.nq.gz
│   ├── 58b82002a8c645f191d474e14bc1b8f0e083fed2.nq.gz
│   ├── 6c54e7a3ba67deb27aa71289434f94e0f176b45d.nq.gz
│   ├── 70d0e5f7b67c65e76ddf1eb5bceb02b1c7247ade.nq.gz
│   ├── 841570ac071f7b6f4cedfc5c49ab03ae898436ed.nq.gz
│   ├── 94ba3d1a6bebdf9f2be167bf8a3711f07e7edefa.nq.gz
│   ├── b0148dbc5eed4f4f37f0ebeaa3572c8c3ad0e9f9.nq.gz
│   ├── ba0829127e0787a994ae719ffeabe4b8ebc2f4e9.nq.gz
│   ├── bbdc65374d1faab700413b3327df613b007743c3.nq.gz
│   ├── c5dc80e1e6759aa6ca75581f3b236730ba90fa0b.nq.gz
│   ├── cfa295f84d348cc9e2b555b2d86cab12a4b6f07e.nq.gz
│   ├── cff246706f3f465efd77a47d7b4d742f875476b1.nq.gz
│   ├── d01642c6e1df930247062b110048851e17050464.nq.gz
│   ├── d310c67968a4a95b96c35636d6003b1ada3a56c7.nq.gz
│   ├── dd99748c64f6f0b44cf71ae6b7acfebf6b8bcce4.nq.gz
│   ├── e1b551480a2ced1f6f64d32f3855bb5a03d45664.nq.gz
│   └── f94b0f41755337b9cc8128c811295ed18479337f.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 400eab094a98da2ab89d33f36f53b039f73d4db2.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

12 directories, 32 files
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

[pola-rs/polars-iceberg](https://github.com/pola-rs/polars-iceberg)

---
*Parsed on 2026-10-10 by [repolex](https://repolex.ai)*
