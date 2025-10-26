# Scripts

このディレクトリは、外部スクリプト（Python、Shell、Node.jsなど）を配置する場所です。

## スクリプトの用途

Claude Codeの組み込みツールだけでは実現できない高度な処理を、外部スクリプトとして実装します：

- 外部API連携（Google Trends、SEO分析ツール）
- 画像処理（最適化、サムネイル生成）
- データ変換（Markdown → PDF、HTML変換）
- バッチ処理（複数記事の一括生成）

## 使用例

将来、以下のようなスクリプトを追加する予定があります：

```
scripts/
├── analyze_keywords.py        # キーワード分析（Google Trends API）
├── optimize_images.py         # 画像最適化（Pillow/ImageMagick）
├── generate_sitemap.py        # サイトマップ生成
├── validate_markdown.sh       # Markdownバリデーション
└── requirements.txt           # Python依存関係
```

## 現在の状態

現在、このプラグインでは外部スクリプトを使用していません。すべての機能はClaude Codeの組み込みツール（WebSearch, Read, Write, Edit）で実装されています。
