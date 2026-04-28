# karpathy-llm-wiki

- **Source**: `sources/2026-04-28_karpathy-llm-wiki.md` ・Andrej Karpathy ・2026-04-28 取得
- **Tags**: #summary #knowledge-management #llm

## TL;DR
RAG は質問のたびにゼロから答えを再発掘するが、LLM Wiki Pattern では LLM が **永続的な Wiki** を増分的に書き続ける。新しいソースが来るたびに既存ページが更新され、相互参照と矛盾の解消が自動で進む。Obsidian は IDE、LLM はプログラマ、Wiki はコードベースという関係。

## キーポイント
- 普通の RAG は「検索→回答」を毎回繰り返すだけで、知識が**蓄積しない**。
- LLM Wiki は **persistent, compounding artifact**：使うほど豊かになる。
- 三層構造: **Raw sources（不変）/ Wiki（LLM が書く）/ Schema（CLAUDE.md 等）**。
- 三オペレーション: **Ingest / Query / Lint**。1 ソースの ingest で 10〜15 ページが更新されうる。
- 二特別ファイル: **`index.md`**（カタログ・content-oriented）と **`log.md`**（時系列・append-only）。
- ユーザはソース選定と質問、LLM は要約・相互参照・整合性維持などの bookkeeping を担う。
- Wiki は単なる git 管理の Markdown 集合 → バージョン管理・分岐・協業がタダで手に入る。

## 引用に値する一節
> Humans abandon wikis because the maintenance burden grows faster than the value. LLMs don't get bored, don't forget to update a cross-reference, and can touch 15 files in one pass.

> Obsidian is the IDE; the LLM is the programmer; the wiki is the codebase.

## 適用領域
個人のジャーナル / 研究の深掘り / 読書メモ / 社内 Wiki / 競合分析・デューデリジェンス・旅行計画など。

## 関連
- [[Andrej Karpathy]]
- [[LLM Wiki Pattern]]
- [[Three-Layer Architecture]]
- [[Ingest Query Lint]]
