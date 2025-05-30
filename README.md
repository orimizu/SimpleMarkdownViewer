# Simple Markdown Viewer / マークダウンビューア

シンプルで使いやすいマークダウンビューアアプリケーションです。単一のHTMLファイルで実行され、マークダウンファイルをドラッグ＆ドロップで素早くプレビューできます。

![Markdown Viewer Screenshot](https://github.com/orimizu/SimpleMarkdownViewer/blob/main/img/SimpleMarkdownViewer.png)

## 特徴

- **単一HTMLファイル**: インストール不要、依存関係なし
- **ドラッグ＆ドロップ対応**: ファイルを簡単に読み込み
- **マークダウン形式を完全サポート**: 見出し、リスト、コードブロック、テーブルなど
- **Mermaid図表対応**: フローチャート、シーケンス図、クラス図などの描画
- **ダークモード対応**: 目に優しい夜間表示モード（Mermaid図表も自動対応）
- **レスポンシブデザイン**: スマートフォンからデスクトップまで対応
- **軽量**: 高速な読み込みと表示

## 使用方法

### オンラインで使用

1. [Markdown Viewer](https://orimizu.github.io/SimpleMarkdownViewer/)にアクセス
2. マークダウンファイル（.md、.markdown、.txt）をドロップエリアにドラッグ＆ドロップ
3. または「ファイルを選択」ボタンをクリックしてファイルを選択

### ローカルで使用

1. このリポジトリをクローンするか、[リリースページ](https://github.com/orimizu/SimpleMarkdownViewer/releases)から最新のHTMLファイルをダウンロード
2. index.htmlをブラウザで開く
3. マークダウンファイルをドロップエリアにドラッグ＆ドロップまたは「ファイルを選択」ボタンから選択

## サポートするマークダウン機能

### 基本的なマークダウン
- 見出し（# h1、## h2など）
- 箇条書きリスト（-、*、+）と番号付きリスト（1.、2.など）
- 強調（**太字**、*イタリック*）
- コードブロック（```言語）とインラインコード（`コード`）
- テーブル
- 引用（> 引用文）
- 水平線（---）
- リンク（[テキスト](URL)）

### Mermaid図表

````markdown
```mermaid
graph TD
    A[開始] --> B{条件判定}
    B -->|Yes| C[処理A]
    B -->|No| D[処理B]
    C --> E[終了]
    D --> E
```
````

**サポートする図表タイプ:**
- **フローチャート**: `graph TD`, `graph LR`, `flowchart`
- **シーケンス図**: `sequenceDiagram`
- **クラス図**: `classDiagram`
- **状態図**: `stateDiagram`
- **ガントチャート**: `gantt`
- **パイチャート**: `pie`
- **ER図**: `erDiagram`
- **ユーザージャーニー**: `journey`
- **Git図**: `gitgraph`
- その他Mermaidがサポートする全ての図表タイプ

## 技術情報

- [Marked.js](https://marked.js.org/): マークダウンパーサー
- [Mermaid.js](https://mermaid.js.org/): 図表レンダリングエンジン
- HTML5 File API: ドラッグ＆ドロップとファイル操作
- CSS3: スタイリングとダークモード
- JavaScript (ES6): インタラクション処理

## ライセンス

[MIT License](LICENSE)

## クレジット

- [Marked.js](https://marked.js.org/) - マークダウンパーサーライブラリ
- [Mermaid.js](https://mermaid.js.org/) - 図表描画ライブラリ

---

* https://github.com/orimizu
* Twitter(X): ryuuri_tweet
* https://youtube.com/@ryuuri

