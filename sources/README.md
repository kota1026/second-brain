# sources/ — 真実の源泉（Immutable）

ここに置いたファイルは **読み込み専用** です。Claude Code は読みますが、書き換え・改名・削除しません。

## 推奨ファイル名

```
YYYY-MM-DD_short-slug.ext
```

例:
- `2026-04-28_karpathy-llm-wiki.md`
- `2026-05-12_meeting-acme-kickoff.txt`
- `2026-06-01_paper-attention-is-all-you-need.pdf`

## 入れて良いもの

- 記事 / 論文 / レポート
- ミーティングの文字起こし
- Obsidian Web Clipper でクリップした Markdown
- Notion からエクスポートしたファイル
- 自分で書いた過去のメモ・原稿
- 画像・データファイル

## してはいけないこと

- 既存の `sources/` ファイルを編集する
- 機密情報をそのまま入れる（必要なら別 Vault を分ける）

新しいソースを追加したら、Claude Code に **「`sources/<file>` を ingest して」** と伝えてください。
詳細は `../CLAUDE.md` を参照。
