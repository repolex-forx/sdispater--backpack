# Repolex Knowledge Graph of sdispater/backpack

RDF knowledge graph data for [sdispater/backpack](https://github.com/sdispater/backpack), parsed by [repolex](https://repolex.ai).

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
rlex download sdispater/backpack
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 764e7f79fd2b1c1ac4883d8e5c9da5c65dfc875e
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 764e7f79fd2b1c1ac4883d8e5c9da5c65dfc875e
│           └── chunk-001.nq.gz
├── blob
│   ├── 1392f056a86fb0f69c31624c33be5b78457b3885.nq.gz
│   ├── 15ebc86b8f141b855fa87788a63af4c1681ab310.nq.gz
│   ├── 26b77f68be53ca5605724cc5dead0e5cd6d4132b.nq.gz
│   ├── 27f5eb8d56e827c6e1cf2f05cbba0eecd56fab47.nq.gz
│   ├── 2a9acf13daa95e85642ea255d3e3bd1ef8252804.nq.gz
│   ├── 2ba212f65f3c251e6e1c1a94966c90969dd310d7.nq.gz
│   ├── 322630ee75f32576be6c69b4de9deb73cddc430c.nq.gz
│   ├── 42949156011871d18d58b0d93c2f75df853d9947.nq.gz
│   ├── 469dd0bac13b438b07a7bbe98769f57f08451dca.nq.gz
│   ├── 4dd82cdddd245753bbdee39d800e4e93f3ab1218.nq.gz
│   ├── 55aa9a50ca84a065941cb6631261c0ca48293943.nq.gz
│   ├── 5d4f076722e8976d76e6cfce8004d2d37c960097.nq.gz
│   ├── 633f866158ac742cf754a2c43edcb07e3a094f3c.nq.gz
│   ├── 701df228d97e9bf3f2b10c5634107daff2f7bd3d.nq.gz
│   ├── 7077e2d0dd13aaebc6ce38d25249e85fe5ba8d65.nq.gz
│   ├── 7b9709a72719579edef0fc71bcd1b1d3229fc1be.nq.gz
│   ├── 9ab7179740261b171363424adb61dbaec67dc59a.nq.gz
│   ├── 9b3dcf7d52414e8764a8260b6f38f97aa255c822.nq.gz
│   ├── a1888a9cec1544200ee4051f86367efbe4d906a8.nq.gz
│   ├── d1203dfd57be7a7f096e533897d4c48311735dbb.nq.gz
│   ├── e3a714f8374c08de1f0c59c176398ce5f0c6622e.nq.gz
│   ├── e749e891fa7b5fb9ab680b5ad8b336ba49ca0614.nq.gz
│   ├── ea82f843c2465f1f5064f7156f77260bc161a237.nq.gz
│   └── f04c343e328b6448b36951cffe53dd3eae351304.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 764e7f79fd2b1c1ac4883d8e5c9da5c65dfc875e.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 32 files
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

[sdispater/backpack](https://github.com/sdispater/backpack)

---
*Parsed on 2026-10-20 by [repolex](https://repolex.ai)*
