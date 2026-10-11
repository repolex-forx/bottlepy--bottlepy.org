# Repolex Knowledge Graph of bottlepy/bottlepy.org

RDF knowledge graph data for [bottlepy/bottlepy.org](https://github.com/bottlepy/bottlepy.org), parsed by [repolex](https://repolex.ai).

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
rlex download bottlepy/bottlepy.org
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 28d8d09387b7eb5de19c3748f7b276d3d356f09e
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 28d8d09387b7eb5de19c3748f7b276d3d356f09e
│           └── chunk-001.nq.gz
├── blob
│   ├── 00957315125c55e98ad95276c6ee53e84c05a78c.nq.gz
│   ├── 1105305850621343d54022dd422415ddf1f659e1.nq.gz
│   ├── 14267e90323cf5175815cfbc34eb6affc59412cb.nq.gz
│   ├── 1465459e6c3b346a3d79c32a3b16cf24c70c40c7.nq.gz
│   ├── 23182caf795a7dbc23b60dd048e31ec16ff823fb.nq.gz
│   ├── 24314f603a3bc44cf66ddf3e0246a0927b9d1179.nq.gz
│   ├── 2bf956565709e6f262e3e5e50e4ace99b25c49c4.nq.gz
│   ├── 333e9de6ef596884d510a3507cb68e872fb9b586.nq.gz
│   ├── 35233e3ccbdc55878d95ef7a95c54b8895ac84e5.nq.gz
│   ├── 4b8c1faf5bd030016fc5153896256fec90e5282b.nq.gz
│   ├── 4c49085d6b928e3f4c261565c6cade1e524424fb.nq.gz
│   ├── 4e2d5597dfc391a8b5e35df786c51c49ac344d91.nq.gz
│   ├── 511478bfc4c793871d1d6b5e775442b91a0f64e4.nq.gz
│   ├── 5e5e3aba3ec9c8edcd308850e28fd189b59f9a4b.nq.gz
│   ├── 6fb7f634a83c5868b5480dce6b14c0dc3bd6df80.nq.gz
│   ├── 7308985e641800b18c59c3180b37a9d6d36f0804.nq.gz
│   ├── 75d46edde1222963efea9e6e4c50848370f39af0.nq.gz
│   ├── 7dbecc9be74d3f4cfd5b2870915148c9a35415ea.nq.gz
│   ├── 821b0ee587c6e9cdd590dd435222b682b1c9aa41.nq.gz
│   ├── 82da06473c76f4c16352d264c3d82ebb0b9c888e.nq.gz
│   ├── accc5cb53fc0362e6b2dcf61e148a6888466e3b4.nq.gz
│   ├── b6b83f12da8eda7f5202f228db6d4fcec59effcd.nq.gz
│   ├── d34aa255cf0de026e987d305026e752cfc5b39da.nq.gz
│   ├── ddff09c15333b4ef9d19136d25ecc561b7fd279f.nq.gz
│   └── f3e5a088349e22dffb58c58e81a0116f344fba43.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 28d8d09387b7eb5de19c3748f7b276d3d356f09e.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 33 files
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

[bottlepy/bottlepy.org](https://github.com/bottlepy/bottlepy.org)

---
*Parsed on 2026-10-11 by [repolex](https://repolex.ai)*
