# Repolex Knowledge Graph of napari/napari-graph

RDF knowledge graph data for [napari/napari-graph](https://github.com/napari/napari-graph), parsed by [repolex](https://repolex.ai).

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
rlex download napari/napari-graph
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── ee3f31cb15e278bc55e6446729579400d7e2a608
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── ee3f31cb15e278bc55e6446729579400d7e2a608
│           └── chunk-001.nq.gz
├── blob
│   ├── 0454b89f8eef172771fd414a3da7ef193bb2d173.nq.gz
│   ├── 07d6cb7479151d9ed2b8eba8ec9ad81ed2204c52.nq.gz
│   ├── 359fa128554efd9aee79f606988669d96cc9ee34.nq.gz
│   ├── 3a12186fa448bc685791b39b56c7dda719a922ea.nq.gz
│   ├── 3c06e65a167f0a0fd1f6898b985ecfa91bb70508.nq.gz
│   ├── 4a4cafe6cc1244fdcbdb98a1d152e56d5fc6f446.nq.gz
│   ├── 4a5faa864a88cba750f0e646fb9d89d87016177c.nq.gz
│   ├── 4aa2de428443ee3e8b564fcd1da216d44bceaf8a.nq.gz
│   ├── 4dca156ef37544cc5d0cb63df1016529707b10ca.nq.gz
│   ├── 4fbc62f6ec8659d5dd4f054580eb2bac4350f3c1.nq.gz
│   ├── 616bebacf682fb989d3b2fae7789b376f1dfca60.nq.gz
│   ├── 6192e3df477220017f3c7f62651280a78db04131.nq.gz
│   ├── 6414004b547979f02ee458dce18fb7a7b3fb03f1.nq.gz
│   ├── 68735cc91956dca12c601802da08e1cd334e7801.nq.gz
│   ├── 75d1010f092536b8a68141b269f982891878d3a8.nq.gz
│   ├── 79ce6d65196714592c308526ac2b4c01f83b128c.nq.gz
│   ├── 7fb30e3950d111d9b563793c565622d08c6def61.nq.gz
│   ├── 81533307422c29135f4e1ddad332fdfc1f97e153.nq.gz
│   ├── bf0e38ac61bfe49484beb45c3ea55642b4841877.nq.gz
│   ├── c1350b5ee9f29c787fd5d12914b451fd5ef2dcb6.nq.gz
│   ├── c35f738cecccc86936ba54406700e5c589012aa7.nq.gz
│   ├── c4357a9b34470e5737e8e98695f210a364a1cfc9.nq.gz
│   ├── c55333cbc1c7bb18404b71634ec37fde5c946ae0.nq.gz
│   ├── c973dc8fa212ae66b9e3369fc3e1435506ff665c.nq.gz
│   └── ca44497dfc342e94e559eee2c2eeb5922a7328c5.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── ee3f31cb15e278bc55e6446729579400d7e2a608.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 33 files
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

[napari/napari-graph](https://github.com/napari/napari-graph)

---
*Parsed on 2026-10-28 by [repolex](https://repolex.ai)*
