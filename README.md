# Repolex Knowledge Graph of colcon/colcon-parallel-executor

RDF knowledge graph data for [colcon/colcon-parallel-executor](https://github.com/colcon/colcon-parallel-executor), parsed by [repolex](https://repolex.ai).

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
rlex download colcon/colcon-parallel-executor
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── bb4e55382bd43be930b512dc437ce000ae607976
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── bb4e55382bd43be930b512dc437ce000ae607976
│           └── chunk-001.nq.gz
├── blob
│   ├── 0f17157ed42b486a0c57cbffddd97987a4844e6b.nq.gz
│   ├── 1dd3c73a4cec13a832cd1d40ef3ebec8a9851445.nq.gz
│   ├── 326bb66d4c74f0cf8cf0dfc4e79909001f37da84.nq.gz
│   ├── 42fb19f2a4fde92de4dfed8c3357c972a2850959.nq.gz
│   ├── 456f6fa6f3024314a0055854db0d9025788cfc77.nq.gz
│   ├── 4ba1d820901a2ae3a9c499aad13dd655fc0ff0e4.nq.gz
│   ├── 50b02dd455c172647e0adced3e7e80148220dac4.nq.gz
│   ├── 5c4cc87af2c8858bb17e96e8db7b07f6aa5187da.nq.gz
│   ├── 7180d98484e91d2617dd9c830e59fd8700c74f46.nq.gz
│   ├── 8d315d51e4f6e4f533a08823b5cc3627e9540cc2.nq.gz
│   ├── ac400861c894e1bd469ba83cce9f296cb2642063.nq.gz
│   ├── c91b5839d69b6bd1ad2bc511d6d26087de9eb797.nq.gz
│   ├── d645695673349e3947e8e5ae42332d0ac3164cd7.nq.gz
│   ├── daf4731d0a19b0dae57d4e9cf16f23a2b6b43948.nq.gz
│   ├── dfc84ffd244404f4db107ea1e36274feb9754853.nq.gz
│   ├── dffe460f162da9929178a7ce342532e7ba896425.nq.gz
│   ├── e1048c6d507f1cceac385a163e1c30cc246809fb.nq.gz
│   ├── e13d5ae1a5ceaa97276f465531ca9337f203760e.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   ├── e82fd0b0abbf1472480d19d468efe7819276e80d.nq.gz
│   └── eb678e35d9f1c30711db08a776f1f670aa7347ec.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── bb4e55382bd43be930b512dc437ce000ae607976.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 29 files
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

[colcon/colcon-parallel-executor](https://github.com/colcon/colcon-parallel-executor)

---
*Parsed on 2026-10-17 by [repolex](https://repolex.ai)*
