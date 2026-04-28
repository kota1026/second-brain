# Second Brain — Claude Code × Obsidian

Andrej Karpathy 提唱の **LLM Wiki Pattern** を Obsidian Vault として実装したリポジトリ。
ソースを入れるたびに Claude Code が Wiki を更新し続け、使うほど賢くなる「AI 第二の脳」になります。

> 普通の RAG は毎回ゼロから検索するだけ。
> このリポジトリは **答えを育て続ける** Wiki を Claude Code に運用させます。

---

## ディレクトリ構成

```
.
├── CLAUDE.md          # AI への憲法（スキーマ・ワークフロー）
├── README.md          # このファイル
├── sources/           # 不変の生資料（Claude は読むだけ）
└── wiki/              # Claude が育てる Markdown
    ├── index.md       # 全ページのカタログ
    ├── log.md         # 時系列の操作ログ（append-only）
    ├── summaries/     # 各ソースの要約（1 ソース = 1 ページ）
    ├── people/        # 人物ページ
    ├── concepts/      # 概念・用語ページ
    ├── comparisons/   # 比較表
    └── overviews/     # 領域横断の俯瞰
```

詳しいルールは [`CLAUDE.md`](./CLAUDE.md) を参照。

---

## 5 分セットアップ

### 1. Obsidian をインストール
<https://obsidian.md/> から OS 用パッケージを入れる。

### 2. このリポジトリを Vault として開く
Obsidian の `Open folder as vault` でリポジトリのルート（`second-brain/`）を選択。
`.obsidian/` 配下のローカル設定は `.gitignore` で除外済み。

### 3. Claude Code でこのフォルダを開く
- ターミナルでリポジトリ直下に `cd` して `claude` を起動、または
- Claude Code デスクトップアプリの「フォルダを選択」から `second-brain/` を選ぶ。

Claude Code は起動時に `CLAUDE.md` を自動で読み込み、Wiki 管理者として振る舞います。

### 4. 最初のソースを入れる
過去のメモ・記事・YouTube 文字起こし・Notion エクスポートなどを `sources/` に放り込む。
ファイル名は `YYYY-MM-DD_short-slug.ext` 推奨。

> このリポジトリは初期状態で **Karpathy の gist 自体を最初のソースとして取り込み済み** です（`sources/2026-04-28_karpathy-llm-wiki.md`）。
> Wiki 側にも `wiki/summaries/karpathy-llm-wiki.md` ・ `wiki/people/Andrej Karpathy.md` ・ `wiki/concepts/{LLM Wiki Pattern, Three-Layer Architecture, Ingest Query Lint}.md` がすでに生えています。動作サンプルとして眺めるか、不要なら削除してご自身のソースで上書きしてください。

### 5. Claude に取り込ませる
```
sources/2026-04-28_my-article.md を ingest して
```
これで `wiki/summaries/`, `wiki/people/`, `wiki/concepts/` などが自動で更新され、
`wiki/index.md` と `wiki/log.md` にも反映されます。

---

## 日々の使い方

| やりたいこと | Claude Code への一言 |
| --- | --- |
| 資料を追加 | `sources/<file> を ingest して` |
| Wiki に質問 | `〜について Wiki から答えて` |
| 比較表が欲しい | `X と Y を比較表にして、よければ wiki に保存` |
| 健康チェック | `lint して` |
| 直近の操作を見る | `grep "^## \[" wiki/log.md \| tail -10` |
| 孤児ページを探す | Obsidian の Graph View → Orphans |

---

## 設計の要点

- **3 層**: `sources/`（不変）/ `wiki/`（AI が書く）/ `CLAUDE.md`（ルール）
- **3 オペレーション**: Ingest / Query / Lint
- **2 特別ファイル**: `wiki/index.md`（カタログ） / `wiki/log.md`（時系列ログ）
- **すべての主張に出典**を付ける。`sources/` は絶対に書き換えない。

詳細は [`CLAUDE.md`](./CLAUDE.md) §1〜§5 にあります。

---

## 参考

- Andrej Karpathy のシステムプロンプト: <https://gist.github.com/karpathy/442a6bf555914893e9891c11519de94f>
- 元になったツイート（すみか＠ClaudeCodeガチ勢, [@sumika45379](https://x.com/sumika45379)）
