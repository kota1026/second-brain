# LLM Wiki Pattern

- **Tags**: #concept
- **一行定義**: LLM が永続的な Markdown Wiki を増分的に書き続けることで、ソースが増えるほど豊かになる知識管理パターン。

## 詳細
普通の RAG（NotebookLM・ChatGPT へのファイルアップロード等）はクエリ時にチャンク検索→生成、を繰り返すため **知識が蓄積しない**。

LLM Wiki Pattern では、新しいソースが来るたびに LLM が:
- 要約ページを作る
- 既存の人物・概念ページを更新する
- 相互参照を張り直す
- 矛盾があれば指摘する
- インデックスとログを更新する

…という **bookkeeping** を全部やる。これにより Wiki が **persistent, compounding artifact** になる。

## 構成要素
- 三層: [[Three-Layer Architecture]]
- 三操作: [[Ingest Query Lint]]
- 二特別ファイル: `wiki/index.md`（content-oriented カタログ）と `wiki/log.md`（chronological append-only）

## なぜ機能するか
> Humans abandon wikis because the maintenance burden grows faster than the value. LLMs don't get bored.

維持コストが実質ゼロに近づくので、Wiki が腐らない。

## 派生・対比される概念
- 対比: 普通の **RAG**
- 系譜: **Vannevar Bush の Memex (1945)**
- 補助ツール: [qmd](https://github.com/tobi/qmd)（ローカル検索）、Obsidian Web Clipper、Marp、Dataview

## 出典
- [[karpathy-llm-wiki]]
