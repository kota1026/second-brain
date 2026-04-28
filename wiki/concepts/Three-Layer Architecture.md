# Three-Layer Architecture

- **Tags**: #concept
- **一行定義**: LLM Wiki を支える Sources / Wiki / Schema の三層分離。

## 詳細

| 層 | 内容 | 編集権限 |
| --- | --- | --- |
| **Raw sources** | 記事・論文・画像・データ等の **不変** な一次資料 | 人間のみ。LLM は read-only |
| **Wiki** | LLM が生成・維持する Markdown 群（要約 / 人物 / 概念 / 比較 / 概観） | LLM が書き、人間が読む |
| **Schema** | `CLAUDE.md` 等の **設定ファイル**。Wiki の構造・規約・ワークフローを定義 | 人間と LLM が共進化させる |

## なぜ三層に分けるか
- Sources を不変にすることで **真実の源泉** を汚染しない。
- Wiki は LLM の作業領域。書き換え・再構成が自由にできる。
- Schema があるから LLM が「汎用チャットボット」ではなく **disciplined wiki maintainer** として動く。

## このリポジトリでの実装
- `sources/` ・ `wiki/` ・ `CLAUDE.md`
- 詳細は [[karpathy-llm-wiki]] §Architecture と `CLAUDE.md` §1 を参照。

## 関連
- [[LLM Wiki Pattern]]
- [[Ingest Query Lint]]

## 出典
- [[karpathy-llm-wiki]]
