# Repolex Knowledge Graph of liluo/pygments-github-lexers

RDF knowledge graph data for [liluo/pygments-github-lexers](https://github.com/liluo/pygments-github-lexers), parsed by [repolex](https://repolex.ai).

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
rlex download liluo/pygments-github-lexers
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 02df3a52c2c93312bab648cf15ea9c642aea9bd7
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 02df3a52c2c93312bab648cf15ea9c642aea9bd7
│           └── chunk-001.nq.gz
├── blob
│   ├── 0154882187f4e81e1b1b45d75ca33125c7168a4e.nq.gz
│   ├── 10ab6313cb50d1cc99d980feb107b3bf2ac870a8.nq.gz
│   ├── 620eec367b4e2b4f7e29f177c45803eafaa3e80d.nq.gz
│   ├── 883b3893d73915d53720a7b3d6b1174b6f7440ea.nq.gz
│   ├── d2d6f360b5d1ea91375f06547df0048ec47a4862.nq.gz
│   ├── d2fa4b2c1c0c58483e973aaf7a7f670b14d5f907.nq.gz
│   └── f8de5d0cf08341e0a4da3084f835a86173866b8a.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 02df3a52c2c93312bab648cf15ea9c642aea9bd7.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 15 files
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

[liluo/pygments-github-lexers](https://github.com/liluo/pygments-github-lexers)

---
*Parsed on 2026-11-06 by [repolex](https://repolex.ai)*
