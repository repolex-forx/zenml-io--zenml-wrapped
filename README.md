# Repolex Knowledge Graph of zenml-io/zenml-wrapped

RDF knowledge graph data for [zenml-io/zenml-wrapped](https://github.com/zenml-io/zenml-wrapped), parsed by [repolex](https://repolex.ai).

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
rlex download zenml-io/zenml-wrapped
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 967aeed55ec25c1ab944aa5b2fc0b481193038f7
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 967aeed55ec25c1ab944aa5b2fc0b481193038f7
│           └── chunk-001.nq.gz
├── blob
│   ├── 2ad3e5fcc6d3dfbb3f0ac4b7c651657b571d01b8.nq.gz
│   ├── 48fa9df4d740867d73df7fbe43db781d4eeec79f.nq.gz
│   ├── 6901018980bb019f807f3c581caa659f8b6918f0.nq.gz
│   ├── 8a25533286a4295aa16293c69cf30edc0fae379b.nq.gz
│   ├── a75ff825e18f640fc79ae755ba1bb40cc953d321.nq.gz
│   ├── be21f30f6191381cb3922546c0211cb01c829ea0.nq.gz
│   ├── c821ebdc1489aee51828bf8c6e0cedb801c24543.nq.gz
│   └── d4c54c013cd4b58e7ce8b9578fed14f0f00aee08.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 967aeed55ec25c1ab944aa5b2fc0b481193038f7.nq.gz
└── tag
    └── tag.nq.gz

11 directories, 14 files
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

[zenml-io/zenml-wrapped](https://github.com/zenml-io/zenml-wrapped)

---
*Parsed on 2026-11-08 by [repolex](https://repolex.ai)*
