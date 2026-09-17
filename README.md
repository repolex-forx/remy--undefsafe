# Repolex Knowledge Graph of remy/undefsafe

RDF knowledge graph data for [remy/undefsafe](https://github.com/remy/undefsafe), parsed by [repolex](https://repolex.ai).

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
lexq download remy/undefsafe
```

This will automatically download essential data files from the last parsed commit. Consult `lexq --moreinfo` for other options, including downloading multiple commits, blobs, etc.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 5d3fa3460e6716ed85dd3d41f4973fcd0896493d
│   │       └── chunk-001.nq.gz
│   ├── lsp
│   │   └── 5d3fa3460e6716ed85dd3d41f4973fcd0896493d.nq.gz
│   └── repolex
│       └── 5d3fa3460e6716ed85dd3d41f4973fcd0896493d
│           └── chunk-001.nq.gz
├── blob
│   ├── 0a6464208148274f1c8e9b05033c73c5a9386014.nq.gz
│   ├── 1e05b2e569142f8e9bf4faf4fa88aff8a286b1be.nq.gz
│   ├── 42c6d7c9f0bc52b14a52bcfc38b161c982fb2d15.nq.gz
│   ├── 46a706bc09c13f5b697315bf50692f42dcd8075c.nq.gz
│   ├── 5f6a848de1d716ecbfe8e743cc2cd835447cd448.nq.gz
│   ├── 72afc00e4d674badf62712ac702048dbdc60d93f.nq.gz
│   ├── 744687805338a7d480ff922d75222b414d8b682f.nq.gz
│   ├── 9e01c9bebe37be1b0217bf89ef704a97ba7a6f85.nq.gz
│   ├── a1ace24a762a27bcee0010afeaceecd44d20778d.nq.gz
│   ├── b47f672fd9451ebe3a3378f4f84166dcdd13fc27.nq.gz
│   ├── be74c90138d8072e07800dfb555174d7522d9ea8.nq.gz
│   ├── bfc4795d3a9440c14a09eea09b1081a279283e37.nq.gz
│   ├── c5b3792d551edd890e0fb6d733d1c5e61369af5b.nq.gz
│   ├── caaf03ae2482776e4bb88c28fc231b60de4caf79.nq.gz
│   ├── ce67f0b8a67729a8e504a40a7b89e6e3529fccd8.nq.gz
│   ├── e6ee8866858f79b90eb2b1ea8d5181fc8a041b74.nq.gz
│   └── ed93c23bbf1ac7ef3b17595d2b51e313e8e6fc53.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── dep
│   └── 5d3fa3460e6716ed85dd3d41f4973fcd0896493d.nq.gz
├── filetree
│   └── 5d3fa3460e6716ed85dd3d41f4973fcd0896493d.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

15 directories, 27 files
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

[remy/undefsafe](https://github.com/remy/undefsafe)

---
*Parsed on 2026-09-17 by [repolex](https://repolex.ai)*
