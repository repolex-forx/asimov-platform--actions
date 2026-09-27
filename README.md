# Repolex Knowledge Graph of asimov-platform/actions

RDF knowledge graph data for [asimov-platform/actions](https://github.com/asimov-platform/actions), parsed by [repolex](https://repolex.ai).

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
rlex download asimov-platform/actions
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── c243fa7055a2a5c2e803ca5df32088f67f1c9393
│   │       └── chunk-001.nq.gz
│   ├── lsp
│   │   └── c243fa7055a2a5c2e803ca5df32088f67f1c9393.nq.gz
│   └── repolex
│       └── c243fa7055a2a5c2e803ca5df32088f67f1c9393
│           └── chunk-001.nq.gz
├── blob
│   ├── 0008031182edcb1391a56cff9b820cc331065595.nq.gz
│   ├── 1c4b6f4f794d4fc9d85675e47263d9aacfbedf2c.nq.gz
│   ├── 4a6b614c7fecc0dd1f15c0c26fde035512287600.nq.gz
│   ├── 4a7b4c6d2af5097f9d1ed7aa7ad5f9078f6b27e5.nq.gz
│   ├── 52d956b85a256c918b344b4c6e20d1a7a3b1893f.nq.gz
│   ├── 8ba11347d7cdc9f613090c3871bdfaa618600278.nq.gz
│   ├── 9644164cc7b4dae39f05a267f83ba2b77866af3b.nq.gz
│   ├── a61c394b41360078f546f2409e80a04a3b119bf8.nq.gz
│   ├── b219759736353497c0c33bfe0e5a3ddbc97f71fa.nq.gz
│   ├── c8d89753487074a5dc47cab5e8a4e47403d734a3.nq.gz
│   ├── d832d4a9cf5ed3fe2d90e9b339a414be9c97a18d.nq.gz
│   ├── de7b3e62b0355adfb9b0017af167b1d97fe987bb.nq.gz
│   └── fdddb29aa445bf3d6a5d843d6dd77e10a9f99657.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── c243fa7055a2a5c2e803ca5df32088f67f1c9393.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 21 files
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

[asimov-platform/actions](https://github.com/asimov-platform/actions)

---
*Parsed on 2026-09-27 by [repolex](https://repolex.ai)*
