# Repolex Knowledge Graph of glue-viz/glue-samp

RDF knowledge graph data for [glue-viz/glue-samp](https://github.com/glue-viz/glue-samp), parsed by [repolex](https://repolex.ai).

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
rlex download glue-viz/glue-samp
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 4843bcfdb31ddd6bf9a0df32f9f1ce458380ad03
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 4843bcfdb31ddd6bf9a0df32f9f1ce458380ad03
│           └── chunk-001.nq.gz
├── blob
│   ├── 01f9c2b763dec8220dccd3da7eebaa77b536c6c2.nq.gz
│   ├── 0c79b1097be1c6ce9b4b8a971f0e4e402ec6a90b.nq.gz
│   ├── 3441c49ef4db3ce6c8102674366d7f1e9ffa4821.nq.gz
│   ├── 495fd00a3d9d490fec8410edb8bf39e16293bd10.nq.gz
│   ├── 61c6bf0af162d8ff9e5d564195b03c261d5482a0.nq.gz
│   ├── 87bed67fcb7b32c2921a28ffc24b3469f4c2723b.nq.gz
│   ├── 8cfa14250954e46d9f14110538e7920a3f0cbf44.nq.gz
│   ├── 8d445604a95ac6a51874b6a1cbc812920719839a.nq.gz
│   ├── 8dcac363c7e9f61adfa27200a30bad277ee95cc3.nq.gz
│   ├── 955a373bb7dfd0f731aafcd09afa5cefdd650d98.nq.gz
│   ├── a3db2a9c11fbc6e3efe2e6ad3fd41bed32a519a8.nq.gz
│   ├── aa24ac2d83128a2d44d07d15530ca5ae4dcdf33f.nq.gz
│   ├── b65c97f338428550d8f5f49686015144109811e3.nq.gz
│   ├── bb49122ab9d228116d7f5ddba3760ca3d721852c.nq.gz
│   ├── d0ba991e69b62f658d6cad1711aa94d857f90c67.nq.gz
│   ├── d1dd32eed87e6912fc38c52078ccc363a95f05a7.nq.gz
│   ├── d8d8ae0b1d0fb7b52e04f4791da3533fd34896c3.nq.gz
│   ├── d903ee605e680982c2e9bcf0ced365a473c3dfab.nq.gz
│   ├── db9991aa3b8a4afbd19ba21fe80f4336d0b8b350.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   └── eefa3597e9bd47ba2c0b720feac03adcc1166112.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 4843bcfdb31ddd6bf9a0df32f9f1ce458380ad03.nq.gz
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

[glue-viz/glue-samp](https://github.com/glue-viz/glue-samp)

---
*Parsed on 2026-10-21 by [repolex](https://repolex.ai)*
