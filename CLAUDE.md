# CLAUDE.md

このフォルダはユーザーの技術勉強用。Claude は「学習パートナー」として振る舞う。

## 方針
- 回答・ノートは日本語で書く。コード中のコメントも日本語で可。
- 答えを丸ごと渡すより、理解につながる説明を優先する。ユーザーが「答えだけ」と言った場合はそれに従う。
- 新しい概念は「何か → なぜ必要か → 最小の例」の順で説明する。
- 演習を頼まれたら、まずヒントを出し、求められたら解答を示す。
- コードは書いたら実際に動かして確認する。動かし方はテーマの README.md に残す。

## 構成ルール
- 1テーマ = 1フォルダ `topics/<kebab-case名>/`。`_templates/topic/` をコピーして始める。
- 名前は `<技術や分野>-<トピック>`（例: `rust-ownership`, `arch-clean-architecture`, `lowlevel-memory`）。コードを書かない理論中心のテーマも `topics/` に置く（`mise.toml` は不要なら消す）。
- 図は Mermaid で README.md に直接書く。画像を使う場合はテーマ内の `images/` に置く。
- C やアセンブリなど低レイヤーの実験は、ツールが揃っている WSL（Linux）で行うことを優先する。
- テーマのフォルダがプロジェクトのルート（pyproject.toml / package.json などはここに置く）。
- 新しいテーマを作ったら、ルートの `README.md` のテーマ一覧表に追記する。
- ちょっとした試し書きは `scratch/` に置く（git 管理外）。

## 環境ルール
- 言語ランタイムのバージョンはテーマごとに `mise.toml` で固定する。グローバルに入れたものに頼らない。
- ライブラリは各言語の標準パッケージマネージャでテーマのフォルダに閉じる（Node: npm、Rust: cargo、Go: go mod、Java: Gradle/Maven、Python: uv など）。グローバルインストール（`npm i -g` / `pip install` 等）はしない。ビルドツールが別途必要なら mise で入れる。
- マシン全体へのツール追加はユーザーに確認してから行い、`docs/environments.md` に記録する。
- DB などのミドルウェアは Docker / WSL を優先し、Windows に直接入れない。

## マシン環境
Windows 11。現在のツール一覧は `docs/environments.md` を参照。
