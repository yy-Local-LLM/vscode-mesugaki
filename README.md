# Mesugaki Sensei（メスガキ先生）

コード書いてる横で煽ってくるVSCode拡張。
(ファイル数制限に達したためZipで入れてありますので解凍が必要です）

## 何ができるの

- **エラー監視**: エラーや警告が出ると煽り通知が飛んでくる
- **スタイル指摘**: 保存時にコードをチェックして、雑な書き方に文句をつけてくる（Diagnosticsとして表示）
- **たまに褒めてくれる**: エラー全部直したら、ツンデレっぽく認めてくれる
- **ステータスバー常駐**: クリックでON/OFF切り替え

## 指摘してくるやつ（JS/TSのみ）

- `var` 使ってる
- 変数名が `a`, `tmp`, `foo`, `hoge` みたいな雑なやつ
- `console.log` 残しっぱなし
- マジックナンバー
- 関数が40行以上
- ネストが深すぎ（5階層以上）
- 100行以上でコメント皆無

## セットアップ

```bash
cd vscode-mesugaki
npm install
npm run compile
```

デバッグ実行するには、VSCodeでこのフォルダ開いて **F5** で拡張ホストが立ち上がる。

パッケージ化して自分の環境に入れる場合：

```bash
npm install -g @vscode/vsce
vsce package
# 出来た .vsix を「拡張機能」>「...」>「VSIXからインストール」で入れる
```

## 設定

- `mesugaki.enabled`: 有効/無効
- `mesugaki.intensity`: `soft` / `normal` / `spicy` — 煽りの強さ
- `mesugaki.styleCheck`: スタイルチェックのON/OFF

## コマンド

- `Mesugaki: 煽りON/OFF`
- `Mesugaki: 褒めて（無理やり）` — 気分が沈んだ時用

## 拡張のヒント

- `src/taunts.ts` に台詞を足せば量が増える
- `src/styleChecker.ts` にルール足せば指摘項目が増える。ちゃんとやるならASTパース（`typescript` パッケージのCompiler API）を使うと精度上がる
- 対象言語は今JS/TSだけ。`TARGET_LANGS` を編集すれば増やせる

(ファイル数制限に達したためZipで入れてありますので解凍が必要です）
