# Repolex Knowledge Graph of pypa/pypa.io

RDF knowledge graph data for [pypa/pypa.io](https://github.com/pypa/pypa.io), parsed by [repolex](https://repolex.ai).

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
rlex download pypa/pypa.io
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── ed988856b2b72d40a2e2712ab56290ca2a433c58
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── ed988856b2b72d40a2e2712ab56290ca2a433c58
│           └── chunk-001.nq.gz
├── blob
│   ├── 00266e9cb098d312cbf9c9084393ceac177ce2c2.nq.gz
│   ├── 17f8e0f501de933e40afee462321493b13e26d1f.nq.gz
│   ├── 1ba734196cacd86fff3ae5a6c1a5a0e5406f4289.nq.gz
│   ├── 23a3f9259d9fc37c11146758937f5db7bc5447bd.nq.gz
│   ├── 354767b0665e36203350ebcbdf4a3dabaa8ad98a.nq.gz
│   ├── 553512353e02720872ea43de17de09d5d8d0981f.nq.gz
│   ├── 6311c0ab812b5c228a0ae976695b8f74c0201168.nq.gz
│   ├── 76b20c9f4aeb7a9dc7e722c8866d9bef127dc84b.nq.gz
│   ├── 99033b3494224c8193cc2f453ff4e551f38fc1b1.nq.gz
│   ├── a229b510ea440bdd963085a1484cbdb0bc618a6c.nq.gz
│   ├── b5a72d0e535db5fc60d29cd7c6cdea74784806f0.nq.gz
│   ├── c39f0e39e2d64c2676aec91e7cd9e03d2a7b8815.nq.gz
│   ├── c9bafe1f83722a026361cd83858bea3bf9322ccd.nq.gz
│   ├── d2260eddf60349d4efea2a2efdc39181680f09b0.nq.gz
│   ├── db214a9ae33987dd827a144b12d85a49147e9f4f.nq.gz
│   ├── e53853c5854df2697edb625049567b5c49b213b6.nq.gz
│   └── e96ac53a72484eb9828ac2cfde7cd9107c5f95c4.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── ed988856b2b72d40a2e2712ab56290ca2a433c58.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 25 files
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

[pypa/pypa.io](https://github.com/pypa/pypa.io)

---
*Parsed on 2026-10-11 by [repolex](https://repolex.ai)*
