# Repolex Knowledge Graph of jshttp/type-is

RDF knowledge graph data for [jshttp/type-is](https://github.com/jshttp/type-is), parsed by [repolex](https://repolex.ai).

> **Note**: This data is experimental and subject to change without notice.

## How to use this data

The easiest way to get started is to install the [lexq](https://github.com/repolex-ai/lexq) query tool using [uv](https://docs.astral.sh/uv/getting-started/installation/).

If you have uv installed, just copy/paste this into your terminal:

```bash
uv tool install git+https://github.com/repolex-ai/lexq
```

This installs lexq onto your system, in your user context. Verify the install:

```bash
lexq --help
```

**lexq is designed to be used primarily by LLMs in a terminal.** Start up your favorite LLM and ask it to use the lexq tool. It's that easy!

To load this repo's data:

```bash
lexq download jshttp/type-is
```

This will automatically download essential data files from the last parsed commit. Consult `lexq --moreinfo` for other options, including downloading multiple commits, blobs, etc.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 4a16e0850ec60234a45c4f546bf759ae161c6a36
│   │       └── chunk-001.nq.gz
│   ├── lsp
│   │   └── 4a16e0850ec60234a45c4f546bf759ae161c6a36.nq.gz
│   └── repolex
│       └── 4a16e0850ec60234a45c4f546bf759ae161c6a36
│           └── chunk-001.nq.gz
├── blob
│   ├── 08586d23386e3b925ea1499b275c115853865bbf.nq.gz
│   ├── 386b7b6946e47bc46f8138791049b4e6a7cef889.nq.gz
│   ├── 3bfd85a781a3738609cbf0fa57a1e9bda276b9ec.nq.gz
│   ├── 4443196281bf36e73a4ca8e47e4700b1bc880d7f.nq.gz
│   ├── 62562b74a3b5a79e82ca417b02e0f597d85f5e2f.nq.gz
│   ├── 6812655c8879f5dc3ff3182ed0741fd8c93b347c.nq.gz
│   ├── 9808c3b2b6602da61eb4afcb4caf33368e3e2bd4.nq.gz
│   ├── cf3015fb3b6ee818a7e76aff5854cde130fc5fe0.nq.gz
│   ├── d23946e607b8d0ea667b7ffefe7e63a68e052df7.nq.gz
│   ├── e77384575189ab7a5451bafaacd97a8e76f3100d.nq.gz
│   ├── f15b98e249d653f23d7e121037bde0eae1817582.nq.gz
│   └── ff1215844c4de1eb21a77a512c71f768ae4e7797.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── dep
│   └── 4a16e0850ec60234a45c4f546bf759ae161c6a36.nq.gz
├── filetree
│   └── 4a16e0850ec60234a45c4f546bf759ae161c6a36.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

15 directories, 22 files
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

## Source repository

[jshttp/type-is](https://github.com/jshttp/type-is)

---
*Parsed on 2026-04-10 by [repolex](https://repolex.ai)*
