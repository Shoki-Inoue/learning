# 環境メモ

マシン全体に入れているツールと、その入れ方の記録。新しく入れたら追記する。

| ツール | 用途 | バージョン | 入れ方 | 追加日 |
|---|---|---|---|---|
| git | バージョン管理 | 2.47.1 | 既存 | - |
| Node.js | JS/TS 実行 | 24.19.0 | 既存 | - |
| Python | Python 実行 | 3.13.1 | 既存 | - |
| VS Code | エディタ | - | 既存 | - |
| WSL | Linux 環境 | - | 既存 | - |
| mise | 言語ランタイムのバージョン管理 | 2026.9.18 | `winget install jdx.mise` + shims を User PATH に追加 | 2026-10-06 |
| uv | Python のパッケージ・仮想環境管理 | 0.12.23 | `winget install astral-sh.uv` | 2026-10-06 |

## 方針
- 言語ランタイムは **mise** でテーマごとにバージョン固定（`topics/<テーマ>/mise.toml`）。
- ライブラリは各言語の標準ツールで管理（Node: npm、Rust: cargo、Go: go mod、Java: Gradle/Maven、Python: uv）。uv は Python 専用。
- DB やミドルウェアなど、Windows に直接入れたくないものは Docker / WSL で動かす。

## メモ
- mise の shims: `%LOCALAPPDATA%\mise\shims` を User PATH の先頭に追加済み。これで `python` / `node` などがフォルダの `mise.toml` に従って切り替わる。
- 更新: `mise self-update` / `uv self update`（winget で入れた場合は `winget upgrade jdx.mise` / `winget upgrade astral-sh.uv`）
