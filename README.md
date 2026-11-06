# Repolex Knowledge Graph of sphinx-contrib/sphinxcontrib-termynal

RDF knowledge graph data for [sphinx-contrib/sphinxcontrib-termynal](https://github.com/sphinx-contrib/sphinxcontrib-termynal), parsed by [repolex](https://repolex.ai).

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
rlex download sphinx-contrib/sphinxcontrib-termynal
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 853621b2a0bedcc9a30558afac157990b429b141
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 853621b2a0bedcc9a30558afac157990b429b141
│           └── chunk-001.nq.gz
├── blob
│   ├── 056a4d8742029b5f9ded11a82eba064130c22e0e.nq.gz
│   ├── 0af9db66857239a0ff444247ce11b26071891ed0.nq.gz
│   ├── 0d65de4df8c63c5b1fd355ccecd0a3141415d909.nq.gz
│   ├── 15ca9e9819dff03dac722dd50c4fa481f88104c2.nq.gz
│   ├── 1c8eeacc371db2d43cabf8bd733742941510a08d.nq.gz
│   ├── 25ea0037d2b211976b61ceaea593a6862843c5fe.nq.gz
│   ├── 2bc5d5f7118646c11eac4472d076e00ffdd1a944.nq.gz
│   ├── 3871e3212f07c6847ae40d5898fb9c3af201a05a.nq.gz
│   ├── 3d3b2a70bf6569cc8f3a717c944b52442f17e5c1.nq.gz
│   ├── 591f2f5bb3e70e27d3f8d5383a5bd8b6b5d2cbfb.nq.gz
│   ├── 5b77c9c98d5a4bce8e13ae869260dfc580be0da7.nq.gz
│   ├── 6b7795930ff88b583f34b4bb760f7a4fc2fcac14.nq.gz
│   ├── 6fec64165f3dfd92bd19b7a2d6a0aa784a013266.nq.gz
│   ├── 7208227ce1462d98255072c4c308e51a6a2533d4.nq.gz
│   ├── 73750c8a3dce1b6e9a39ac170c5ca48c48262970.nq.gz
│   ├── 73793bedcdf8166fa0b14101c44384b5348b710e.nq.gz
│   ├── 7a7d3aa00f7473a391afaf6915d53f82add64ca0.nq.gz
│   ├── 8237ac85582b45e76e6ce6e1b71afae48c107bc8.nq.gz
│   ├── 827d0738dc10284f7551bcd10c589d0e80f0610b.nq.gz
│   ├── 8287c4a2304b2b00b765bb43d1bcd7a702fab093.nq.gz
│   ├── 855ef61dea8cc2b64c66485631574e393a14d0cc.nq.gz
│   ├── 872dcf49ca0b5b9a3256e4e1cd2b3cb6bb5d9477.nq.gz
│   ├── 895d2700b2a5725be59bc3c826c4c0880318e7f4.nq.gz
│   ├── 8d623501e9a76a7605bbcb5974a1e811da820e9b.nq.gz
│   ├── 9d91f1701e434d8b7372d201069f771b5478bc75.nq.gz
│   ├── a305549e6b86c65a6d3e029eb51772820d11d6c5.nq.gz
│   ├── b5ab3548129aaf249274af426ad2b55840317f0c.nq.gz
│   ├── bb082a13f72309fe186e22e4f7d7b4d0cb268cc2.nq.gz
│   ├── c16b575addc40f479ee27e4e1076647660a58d23.nq.gz
│   ├── de09d048c1e869dccf0e2f59753a85fbcec66cf0.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   ├── ee7aa59dc260aa45dfcbd0c3497c88d12e50911a.nq.gz
│   ├── f5c90c8de8f454101302a3ebdf34f1bfb1d72514.nq.gz
│   └── f9c309e0b4fcd39242dabd1d593cd7877b7493fb.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 853621b2a0bedcc9a30558afac157990b429b141.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 42 files
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

[sphinx-contrib/sphinxcontrib-termynal](https://github.com/sphinx-contrib/sphinxcontrib-termynal)

---
*Parsed on 2026-11-06 by [repolex](https://repolex.ai)*
