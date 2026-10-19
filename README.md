# Repolex Knowledge Graph of hynek/pem

RDF knowledge graph data for [hynek/pem](https://github.com/hynek/pem), parsed by [repolex](https://repolex.ai).

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
rlex download hynek/pem
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 91ec16ac3b1915ebf0009d203fb7165533d6d943
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 91ec16ac3b1915ebf0009d203fb7165533d6d943
│           └── chunk-001.nq.gz
├── blob
│   ├── 057262b1bf99fb4b228fa07524df1aebc58c0046.nq.gz
│   ├── 19b1fb7cc6e44d049af5f7a2691f2518ab5a60ba.nq.gz
│   ├── 2b57c0224865d8b42f7f06713a280e2749290884.nq.gz
│   ├── 2f5c6bcde31973c81cad42676d5944aaeaf6fa2a.nq.gz
│   ├── 342f4fd1cfde59e0083174913d184fdbb02eb2ca.nq.gz
│   ├── 3b7cf3dc2c7b8e83a8e66f6d780d42ebff880f1d.nq.gz
│   ├── 44f269ad671774c67015d24bc0db3e1227719fd6.nq.gz
│   ├── 4ea5947260ff41d7d2ccbc116b6404066f369c87.nq.gz
│   ├── 52a400e89369917bc29f4f7e7325ee941edb49ef.nq.gz
│   ├── 5adb31d91528699597acc2d384058e2407be91f8.nq.gz
│   ├── 5bae2eb0cfa9d64e90a432aa2b66fdc9fbcc523d.nq.gz
│   ├── 5dea1d70afd41326e113e17e5d57d681e601789f.nq.gz
│   ├── 6324d401a069f4020efcf0ff07442724b52f47c2.nq.gz
│   ├── 66efc0fecd1554e6e4681fcb149692591f388bf2.nq.gz
│   ├── 6b418032735a3a10a807224feeca0e81fb596334.nq.gz
│   ├── 704e787c07d0a0b002579febe0da416d9f8fa346.nq.gz
│   ├── 769ea8aed4ea111572aed07179b2e38bf42b9dc1.nq.gz
│   ├── 7c5100942aae489ca04d07d2c69a4d8f6f8470fe.nq.gz
│   ├── 8c14ddd34788674c542c6b701c5b1f85b553015c.nq.gz
│   ├── 90d906724ac37ccba853a7decf6c5923e2f4dd11.nq.gz
│   ├── 94ad941b178d478c528ef0bb1c9e8e358e31d9b6.nq.gz
│   ├── a38d0249ba67f4b8f455a21c4728703d05fc2f54.nq.gz
│   ├── a87fac9b860945ec3b41def1b2ee00b6e27ce2da.nq.gz
│   ├── b1c05bccf46455c5990735fc38448ba391cc2f5c.nq.gz
│   ├── b70e02df791a6cbd2e2489b58402fda0159076c7.nq.gz
│   ├── ba61f844d4516a5c896f492eb6c3a4a1c910e7fc.nq.gz
│   ├── c02325264b98f8387099d84f0c991cdc42a1fb80.nq.gz
│   ├── c327d011a654914e7706db88a76cbc6563b3621a.nq.gz
│   ├── c3d32a61ef222b520b7dd8ea4af5e1dc32e92745.nq.gz
│   ├── cd46bd07565aa2cf3aab3580363284ba2fac0458.nq.gz
│   ├── db89e2aaeba45e7bf9ecd491e4dc6178520cb7ca.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   ├── ea955f4a0fe4c01f431482fdb750e9c3bca1e226.nq.gz
│   ├── ec8c33334fee0c7b5da22af531a3394e02f63023.nq.gz
│   ├── eceb69672a0d80992bc2044c61565cad53de01e0.nq.gz
│   ├── efd722f1f816e398a0ff9e9c8e378417bf73cf5e.nq.gz
│   ├── f514cc396abc9b0494449ca1cad12126e8ae8e99.nq.gz
│   ├── f78d24693d089263db29c5dd55c7d16826f5a813.nq.gz
│   ├── f96adec4377b32b588c9dc8c422970fcf052dd3e.nq.gz
│   └── fac5b6f08b57dcf94ce7890f31ac62eb811647f8.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 91ec16ac3b1915ebf0009d203fb7165533d6d943.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 48 files
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

[hynek/pem](https://github.com/hynek/pem)

---
*Parsed on 2026-10-19 by [repolex](https://repolex.ai)*
