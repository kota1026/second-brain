# Log — 時系列の操作ログ

**追記専用**。過去のエントリを書き換えないこと。
Unix grep で抽出できるように、各エントリは `## [YYYY-MM-DD] <op> | <タイトル>` で始める。

```
grep "^## \[" wiki/log.md | tail -5
```

---

## [2026-04-28] ingest | Karpathy "LLM Wiki" gist

- ソース: `sources/2026-04-28_karpathy-llm-wiki.md`
- 影響したページ: [[karpathy-llm-wiki]], [[Andrej Karpathy]], [[LLM Wiki Pattern]], [[Three-Layer Architecture]], [[Ingest Query Lint]]
- メモ: Wiki の最初のソースとして Karpathy 本人の gist を取り込み。サマリー 1 / 人物 1 / 概念 3 を新規作成。`index.md` を初期化。
