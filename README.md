# Repolex Knowledge Graph of simonw/llm-ollama

RDF knowledge graph data for [simonw/llm-ollama](https://github.com/simonw/llm-ollama), parsed by [repolex](https://repolex.ai).

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
rlex download simonw/llm-ollama
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 4c91d4544ae6267ffa5670ed07c928797c7ee11e
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 4c91d4544ae6267ffa5670ed07c928797c7ee11e
│           └── chunk-001.nq.gz
├── blob
│   ├── 261eeb9e9f8b2b4b0d119366dda99c6fd7d35c64.nq.gz
│   ├── 3e8347563081421c650dca467584d3f81e230be8.nq.gz
│   ├── 4e5890f3172ed2ee4e41e1cd99ca9d9e3de7934f.nq.gz
│   ├── 525c10128068e2278189ff40f4afea0831efd488.nq.gz
│   ├── 613021d45f6cca11d48004b56c28526d752e6637.nq.gz
│   ├── 748b127b5c59b27ff8214e61c508b34b93041e14.nq.gz
│   ├── 8d3c8baf0da0978d447010f958db3e6114288f6d.nq.gz
│   ├── a6fbf3619f7036eb83f6a5e7cf503f32029aa562.nq.gz
│   ├── b8f4e032113f33e1d99d03b08284865a90931f1d.nq.gz
│   ├── d71e6f75dc3f9a5ba0284d063891257e142b40d8.nq.gz
│   ├── e024c939b93fe41991caf9e50a1bdbe68a0cee5d.nq.gz
│   ├── e7fcaf6f29868464a641353a49cc0e023050ebb5.nq.gz
│   ├── f0109af7d82942194aa836bf94b71f75e6d02452.nq.gz
│   └── f989c2ee24b053627495adf50a9f24c4f6cd9603.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 4c91d4544ae6267ffa5670ed07c928797c7ee11e.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

12 directories, 21 files
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

[simonw/llm-ollama](https://github.com/simonw/llm-ollama)

---
*Parsed on 2026-10-15 by [repolex](https://repolex.ai)*
