# Commands

このディレクトリは、スラッシュコマンド（Slash Commands）を配置する場所です。

## スラッシュコマンドとは？

スラッシュコマンドは、Claude Code内で `/command-name` という形式で実行できるショートカットです。

## 使用例

将来、以下のようなカスタムコマンドを追加する予定があります：

```
commands/
├── blog-quick-start.md        # /blog-quick-start - クイックスタートガイド実行
├── blog-full-workflow.md      # /blog-full-workflow - 完全ワークフロー実行
└── blog-seo-check.md          # /blog-seo-check - SEOチェック実行
```

各コマンドは、Markdownファイルとして定義されます：

```markdown
---
name: blog-quick-start
description: ブログ記事のクイックスタート（テーマ入力から記事完成まで）
---

# Blog Quick Start Command

このコマンドは、ブログ記事作成の全プロセスを自動実行します。

1. テーマをユーザーから取得
2. ExpertAnalystAgentでアウトライン作成
3. TechnicalWriterAgentで本文執筆
4. CredibilityEnhancerAgentで信頼性強化
5. SEO最適化
6. Markdown整形
```

## 現在の状態

現在、このプラグインではカスタムスラッシュコマンドを定義していません。エージェント（`@expert-analyst`）とスキル（`/markdown-formatter`）を個別に呼び出す形式です。
