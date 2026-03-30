# claude-contract-drafter

Claude Code 用の契約書自動生成テンプレート。

社内でよく使う契約書のひな形を保存しておき、Claude が状況に応じて加筆・修正し、.docx で出力します。

## できること

- 状況を説明するだけで、必要な契約書の種類を判断
- 議事録を読み込ませると、合意事項から必要書類を自動抽出
- ひな形をベースに、当事者情報や条件を反映した契約書を生成
- 条項レベルでの加筆・修正・削除
- .docx 形式での出力

## 使い方

### 1. セットアップ

```bash
git clone https://github.com/issey-hedell/claude-contract-drafter.git
cd claude-contract-drafter
```

### 2. ひな形を用意

`templates/` ディレクトリに、自社で使う契約書のひな形を配置します。

```
templates/
├── 秘密保持契約書.md
├── 業務委託基本契約書.md
├── 金銭消費貸借契約書.md
└── ...
```

対応フォーマット: Markdown (.md) / Word (.docx) / テキスト (.txt)

### 3. Claude Code を起動

```bash
claude
```

起動すると自動的にヒアリングが始まります。

### 使用例

**直接説明する場合:**
```
> A社と業務委託契約を結びたい
```

**議事録を渡す場合:**
```
> この議事録を読んで、必要な契約書を教えて
> [ファイルを渡す]
```

## ディレクトリ構成

```
claude-contract-drafter/
├── CLAUDE.md              # Claude Code への指示（メインプロンプト）
├── README.md              # このファイル
├── templates/             # 契約書のひな形（ユーザーが用意）
│   └── README.md
├── rules/                 # 取引パターン → 必要書類マッピング
│   └── contract-patterns.md
├── output/                # 生成した契約書の出力先
└── docs/                  # プロジェクトドキュメント
```

## カスタマイズ

### ひな形の追加

`templates/` にファイルを追加するだけ。Claude が自動的に認識します。

### 取引パターンの追加

`rules/contract-patterns.md` に新しいパターンを追記すると、Claude の書類判断の精度が上がります。

## 注意事項

- 生成された契約書は必ず法務専門家のレビューを受けてください
- 本ツールは契約書のドラフト支援であり、法的助言を提供するものではありません
- ひな形の品質が出力の品質に直結します

## ライセンス

MIT
