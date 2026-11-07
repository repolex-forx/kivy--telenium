# Repolex Knowledge Graph of kivy/telenium

RDF knowledge graph data for [kivy/telenium](https://github.com/kivy/telenium), parsed by [repolex](https://repolex.ai).

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
rlex download kivy/telenium
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 92300fbf6b0661b16f6d6c4da3fabe719d2c473e
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 92300fbf6b0661b16f6d6c4da3fabe719d2c473e
│           └── chunk-001.nq.gz
├── blob
│   ├── 018b1fed4de4c50145d6f00d6b19c7549b7de1bb.nq.gz
│   ├── 0c75e5ed7d737c1a14321d5cc7317f196b731aa4.nq.gz
│   ├── 1413fc609ab6f21774de0cb7e01360095584f65b.nq.gz
│   ├── 1c88b71e8bf09ce03fa34d123ac55bf727cc3c55.nq.gz
│   ├── 26f39d20e44eaae8bc0a810c6b312c732925bcd5.nq.gz
│   ├── 2e8acdcc55d9e6ddf141780b727a71bf35305157.nq.gz
│   ├── 2fd84f36ebefeecb6ebd7780cbccf9b69b95add2.nq.gz
│   ├── 376880c49b1292e085748494ebcf44aaf1622aa0.nq.gz
│   ├── 4f6ebba1da8559abf3b2f2bcd7667ce3383f6a89.nq.gz
│   ├── 5a12d631732892b7f236fdda9acbd21edfa0c19a.nq.gz
│   ├── 64539b54c3751a6d9adb44c8e3a45ba5a73b77f0.nq.gz
│   ├── 69c86f6117fa87472bd2eeb3410f2963fea378da.nq.gz
│   ├── 6fd2415116556fbc9b5b89d3f76107e6680af0c5.nq.gz
│   ├── 726d9de83f8e5a0c16cc0a6a9592317048a4b24c.nq.gz
│   ├── 7669a34b7be5375107d5ef95e6a86b2755231bf8.nq.gz
│   ├── 7bbbc802f79b87b70a2607b102a838aa6aecb6c3.nq.gz
│   ├── 94fb5490a2ed10b2c69a4a567a4fd2e4f706d841.nq.gz
│   ├── 9e612858f802245ddcbf59788a0db942224bab35.nq.gz
│   ├── a3ecab7d7c494c119083bb49403c4639b412dd9f.nq.gz
│   ├── b0fdfcbf9bfa064592dd7b2e3910315ccf58fba7.nq.gz
│   ├── b93a4953fff68df523aa7656497ee339d6026d64.nq.gz
│   ├── bb1ac86d687b4b9bf7dae90ec60015e8468663f7.nq.gz
│   ├── c29d21ea0c54014a16fee074f72adb8895fea582.nq.gz
│   ├── c953b84d25b1b15ba9025c6f826d0e35d7f6192e.nq.gz
│   ├── ce276ff11540a82b22f64e8d71615fd3c1829cc7.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   └── fb15e3d69c352f7e0a7fc4c20fb9d16721a05171.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 92300fbf6b0661b16f6d6c4da3fabe719d2c473e.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 35 files
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

[kivy/telenium](https://github.com/kivy/telenium)

---
*Parsed on 2026-11-07 by [repolex](https://repolex.ai)*
