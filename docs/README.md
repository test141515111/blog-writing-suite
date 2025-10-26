# Documentation

このディレクトリは、プラグインの詳細ドキュメントを配置する場所です。

## ドキュメントの種類

### 1. API仕様書
エージェントとスキルのAPI仕様を詳細に記述します。

```
docs/
├── api/
│   ├── agents.md              # エージェントAPI仕様
│   ├── skills.md              # スキルAPI仕様
│   └── tools.md               # 使用可能なツール一覧
```

### 2. 設計ドキュメント
プラグインのアーキテクチャと設計思想を記述します。

```
docs/
├── design/
│   ├── architecture.md        # アーキテクチャ概要
│   ├── workflow.md            # ワークフロー設計
│   └── decisions.md           # 設計判断の記録（ADR）
```

### 3. チュートリアル
ステップバイステップの詳細ガイドを提供します。

```
docs/
├── tutorials/
│   ├── 01_getting_started.md          # はじめてのブログ記事執筆
│   ├── 02_advanced_workflows.md       # 高度なワークフロー
│   ├── 03_customization.md            # カスタマイズ方法
│   └── 04_troubleshooting.md          # トラブルシューティング
```

### 4. リファレンス
各コンポーネントの詳細リファレンスを提供します。

```
docs/
├── reference/
│   ├── expert_analyst.md              # ExpertAnalystAgent詳細
│   ├── technical_writer.md            # TechnicalWriterAgent詳細
│   ├── credibility_enhancer.md        # CredibilityEnhancerAgent詳細
│   ├── markdown_formatter.md          # Markdown Formatter詳細
│   ├── blog_article_generator.md      # Blog Article Generator詳細
│   └── seo_optimizer.md               # SEO Optimizer詳細
```

## ドキュメントのビルド

将来的に、MkDocsやSphinxを使用してドキュメントサイトを構築する予定です。

```bash
# MkDocsでドキュメントをビルド
mkdocs build

# ローカルでプレビュー
mkdocs serve
```

## 現在の状態

現在、このディレクトリには詳細ドキュメントが配置されていません。プラグインの基本的な使用方法は、ルートの`README.md`に記載されています。
