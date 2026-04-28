# Ingest Query Lint

- **Tags**: #concept
- **一行定義**: LLM Wiki に対する三つの基本操作。

## 詳細

### Ingest
新ソースを `sources/` に置き、LLM に処理させる。
1. ソースを読む
2. ユーザとキーポイントを確認
3. `wiki/summaries/<slug>.md` を作成
4. 関連する人物・概念ページを **10〜15 個** 同時に更新
5. `wiki/index.md` と `wiki/log.md` を更新

> 「サマリーだけ書いて終わり」にしないのが肝。1 ソースで Wiki 全体が育つ。

### Query
Wiki に質問する。
1. **必ず最初に `wiki/index.md` を読む**
2. 関連ページを読み、引用付きで答える
3. 出力形式は自由（Markdown / 比較表 / Marp スライド / matplotlib / Obsidian Canvas）
4. 価値ある回答は **そのまま `wiki/` に保存** することで探索が積み上がる

### Lint
定期的な健康チェック。
- ページ間の矛盾
- 古くなった主張
- 孤児ページ（inbound link なし）
- 概念は登場するがページが無い場所
- 相互参照漏れ
- データのギャップ

修正は **提案にとどめ**、ユーザの承認を得てから書く。

## 関連
- [[LLM Wiki Pattern]]
- [[Three-Layer Architecture]]

## 出典
- [[karpathy-llm-wiki]]
