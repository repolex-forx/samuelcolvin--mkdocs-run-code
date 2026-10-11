# Repolex Knowledge Graph of samuelcolvin/mkdocs-run-code

RDF knowledge graph data for [samuelcolvin/mkdocs-run-code](https://github.com/samuelcolvin/mkdocs-run-code), parsed by [repolex](https://repolex.ai).

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
rlex download samuelcolvin/mkdocs-run-code
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 9a39e6b22ca2199516cc2eee047189934f8d7a88
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 9a39e6b22ca2199516cc2eee047189934f8d7a88
│           └── chunk-001.nq.gz
├── blob
│   ├── 178135c2b27855a27d4109630473696c869f5ed7.nq.gz
│   ├── 20abfac3247e7ae52683b0c22824b09aa8fd3c87.nq.gz
│   ├── 41a755f8e95f10816603a889e7d21417a3475f74.nq.gz
│   ├── 587484dfa80958570fc1a515b71ccd717793ab34.nq.gz
│   ├── 6c895cec2b659803558c6de2efd670514eebe91b.nq.gz
│   ├── 8e44b942e27391441d152a1f15dc76745391c722.nq.gz
│   ├── a06f484938bd512a1f93632aa1e44cf8c9754751.nq.gz
│   ├── bd99fb36d4caa6a36d9048dd2ed807d814a26d1c.nq.gz
│   ├── d76c9648f80751d683c3671ba90011bc708d618e.nq.gz
│   ├── dcc7c085964337920c3db560afb1da44141dedca.nq.gz
│   ├── dd8f35c980595c09868cae02a6d6250eb76aed6e.nq.gz
│   └── e720f31a24d750e67fdf74bef32af621e97512f3.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 9a39e6b22ca2199516cc2eee047189934f8d7a88.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 20 files
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

[samuelcolvin/mkdocs-run-code](https://github.com/samuelcolvin/mkdocs-run-code)

---
*Parsed on 2026-10-11 by [repolex](https://repolex.ai)*
