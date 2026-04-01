# Repolex Knowledge Graph of tokio-rs/tokio-core

RDF knowledge graph data for [tokio-rs/tokio-core](https://github.com/tokio-rs/tokio-core), parsed by [repolex](https://repolex.ai).

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
lexq download tokio-rs/tokio-core
```

This will automatically download essential data files from the last parsed commit. Consult `lexq --moreinfo` for other options, including downloading multiple commits, blobs, etc.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── blob
│   ├── 159985c491b7d338a0aceb45eb3f2aea9609b1b8.nq.gz
│   ├── 16fe87b06e802f094b3fbb0894b137bca2b16ef1.nq.gz
│   ├── 1d39543d5a93cb2f5398e584b30de6be6d5b1cb0.nq.gz
│   ├── 1e9f9e3387341ac8cd5634623d2a511e8fd52f63.nq.gz
│   ├── 262b4f7ad0875aeffec471f3f8d603bb9094c5a9.nq.gz
│   ├── 28e630cf40d23e85e1b1c48eea4c7c2e8afd90f9.nq.gz
│   ├── 3884a30b5686695e3e760655e5dfe84bf1b372d6.nq.gz
│   ├── 409ec8c385a2f1d6931aa50d5b211b7a7aa208f5.nq.gz
│   ├── 4e2373aa530eb3b66366b11e908f597e93c5d5e4.nq.gz
│   ├── 63d5a82a5919cd09ffd517d678e1f1157c8caf35.nq.gz
│   ├── 6d031623b3203f8f1b55d029232397dd73135aec.nq.gz
│   ├── 75c11da0d911bdca568febdd77859fbbe453f235.nq.gz
│   ├── 7893bbb7e36954d7cb917216c982f3551bd9d778.nq.gz
│   ├── 7efbf54b140e356edd9361b737b31d2b89418215.nq.gz
│   ├── 819fe4ed248f098d15a3e73d230bf786f1a3a24a.nq.gz
│   ├── 83c5a8390e105036bd58b2b6fb0b018a9cea4bc3.nq.gz
│   ├── 85c1d410701caf9fe84c1dd6d677b65ea605bdaa.nq.gz
│   ├── 91edb58d2337e18470ddf71f75524cd83b15535f.nq.gz
│   ├── 929c5962ede486bd273a2ac7d11797ae3c2fdb0f.nq.gz
│   ├── 93d37d56d54403ec5127c583ae6d5ded72ceaa5f.nq.gz
│   ├── 94782e5f586ae3ef3cda9e997956d81f641f0564.nq.gz
│   ├── 949db4750c2b372ef8b4fc591f85b5b71f3a7d03.nq.gz
│   ├── 953ab87a73f6ad9b8ca7035e9de3c35ac5b3a2bb.nq.gz
│   ├── 9637e42a99572a58e21aa6450e87ea5bb2d6ce82.nq.gz
│   ├── 98b38716b7fce9db464d8848da7a7727508b4097.nq.gz
│   ├── a9d37c560c6ab8d4afbf47eda643e8c42e857716.nq.gz
│   ├── ae91ca2749c644f3b4d30137cc43cf58d198c8f2.nq.gz
│   ├── b3b4b8d77acf3f1087d9d2a1816f6ad0c4f492f4.nq.gz
│   ├── b913748f1f7432d0f5f333520167b07f06fe085c.nq.gz
│   ├── bb0cea1352723c9ace8eb636a8c8f4d87f70a545.nq.gz
│   ├── c5b0ef57dbd0769e90699eb87dd63beaefd9c822.nq.gz
│   ├── c61360990e26c4fd5ac27e335250e8f4f564fd89.nq.gz
│   ├── cf441e5d29eef27f495c6b143a68a5515f807f68.nq.gz
│   ├── d22d4a63a6becd4edde901aec8fa48639a228fba.nq.gz
│   ├── d5e2ffe3bb03241469f1e1f96951986c2cdb853a.nq.gz
│   ├── dac363d1ceade69a1614d0e16ff03f20d55a3f54.nq.gz
│   ├── e3ddd3935944f62ec5fa958789804d1b70e85b0e.nq.gz
│   ├── f65164c0865665e2f6b7d724291fe04c38829ac1.nq.gz
│   ├── fcc22181c849974946eae3dacbbf9e0eec768686.nq.gz
│   └── fe8071de7b96fb99d2d0d2db621d9d57d63a0fad.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 550dc76bbdd075ee63bf7b23d4502d03814a5e77.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

8 directories, 46 files
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

[tokio-rs/tokio-core](https://github.com/tokio-rs/tokio-core)

---
*Parsed on 2026-04-01 by [repolex](https://repolex.ai)*
