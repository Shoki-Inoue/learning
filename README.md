# learning

技術勉強用のリポジトリ。ノートとコードを同じ場所で管理する。

## 構成

```
learning/
├── topics/<テーマ>/   # 1テーマ = 1プロジェクト。ノートとコードを同居させる
│   ├── README.md      # 学習ノート + 動かし方
│   ├── mise.toml      # このテーマのランタイムバージョン（必要なら）
│   └── ...            # コード（pyproject.toml, package.json, src/ など自由に）
├── books/<書名>/      # 本ごとの読書ノート（章ごとに chNN.md）
├── scratch/           # 使い捨ての試し書き（git 管理外）
├── docs/              # 全体のメモ（roadmap.md: 学習方針 / environments.md: 環境）
└── _templates/        # 新テーマ（topic/）・本（book/）のひな形
```

## 新しいテーマの始め方

```sh
cp -r _templates/topic topics/<テーマ名>
cd topics/<テーマ名>
# mise.toml で使う言語を有効にして → mise install
```

## テーマ一覧

| テーマ | 環境 | 開始日 | 状態 |
|---|---|---|---|
| | | | |
