# Blog Writing Suite Plugin

<p align="center">
  <img src="https://img.shields.io/badge/version-1.0.0-blue.svg" alt="Version">
  <img src="https://img.shields.io/badge/license-MIT-green.svg" alt="License">
  <img src="https://img.shields.io/badge/Claude_Code-Compatible-purple.svg" alt="Claude Code">
  <img src="https://img.shields.io/badge/PRs-welcome-brightgreen.svg" alt="PRs Welcome">
</p>

ブログ記事執筆のための統合プラグインです。3つの専門エージェントと3つのスキルを含み、記事執筆プロセス全体をサポートします。

---

## ✨ 特徴

- 🤖 **3つの専門エージェント**: テーマ分析、本文執筆、信頼性強化を分業
- 🛠️ **3つの強力なスキル**: Markdown整形、記事生成、SEO最適化
- 🚀 **統合ワークフロー**: エージェント連携による高品質記事生成
- 📊 **SEO最適化**: キーワードリサーチと構造最適化を自動実行
- 🎯 **拡張可能**: hooks, scripts, commands, mcpによる柔軟なカスタマイズ

---

## 📦 インストール

### GitHub経由（推奨）

```bash
# Claude Code CLIでインストール
claude plugin install https://github.com/YOUR_USERNAME/blog-writing-suite

# または手動でクローン
git clone https://github.com/YOUR_USERNAME/blog-writing-suite.git ~/.claude/plugins/blog-writing-suite
```

### ローカル開発

```bash
# リポジトリをクローン
git clone https://github.com/YOUR_USERNAME/blog-writing-suite.git
cd blog-writing-suite

# プロジェクトの.claude/pluginsにシンボリックリンクを作成
ln -s $(pwd) /path/to/your/project/.claude/plugins/blog-writing-suite
```

---

## 🚀 使い方

### クイックスタート

```bash
# Claude Codeを起動
claude

# エージェントを使った記事作成ワークフロー
@expert-analyst "Claude Codeのプラグイン機能について技術記事を書きたい"
# → 詳細なアウトラインが生成されます

@technical-writer "上記のアウトラインに基づいて本文を執筆してください"
# → 完成した記事本文が生成されます

@credibility-enhancer "記事に参考文献とデータソースを追加してください"
# → 学術的信頼性が強化されます

# スキルでSEO最適化と整形
/seo-optimizer "この記事を「Claude Code プラグイン」で最適化してください"
/markdown-formatter "最終整形してください"
```

### エージェント詳細

#### 1. ExpertAnalystAgent（専門家アナリスト）

テーマ分析とアウトライン設計の専門家です。

**機能:**
- テーマの深掘り分析
- 読者ペルソナ設定
- 詳細アウトライン作成
- キーワード戦略策定

**使用例:**
```bash
@expert-analyst "Next.js 14のApp Routerについての記事を書きたい"
```

#### 2. TechnicalWriterAgent（技術ライター）

アウトラインに基づく本文執筆の専門家です。

**機能:**
- わかりやすい専門用語の説明
- 具体例とコード例の提示
- 読みやすい構成の実現
- 論理的な文章展開

**使用例:**
```bash
@technical-writer "ExpertAnalystAgentのアウトラインに基づいて記事を執筆してください"
```

#### 3. CredibilityEnhancerAgent（信頼性強化担当）

記事の信頼性を強化する専門家です。

**機能:**
- 参考文献の整理と引用
- データソースの追加
- 著者プロフィール作成
- 用語集の作成

**使用例:**
```bash
@credibility-enhancer "記事に学術的信頼性を追加してください"
```

### スキル詳細

#### 1. markdown-formatter

Markdownファイルの整形と最適化を実行します。

```bash
/markdown-formatter "README.mdを整形してください"
```

#### 2. blog-article-generator

ブログ記事の体系的生成（テーマ分析〜SEO最適化）を実行します。

```bash
/blog-article-generator "技術記事を生成してください"
```

#### 3. seo-optimizer

SEO最適化（キーワードリサーチ、メタディスクリプション、見出し構造）を実行します。

```bash
/seo-optimizer "記事をSEO最適化してください"
```

---

## 📂 ディレクトリ構造

```
blog-writing-suite/
├── .claude-plugin/
│   └── plugin.json              # プラグインメタデータ
├── agents/
│   ├── expert-analyst.md        # 専門家アナリスト
│   ├── technical-writer.md      # 技術ライター
│   └── credibility-enhancer.md  # 信頼性強化担当
├── skills/
│   ├── markdown-formatter/      # Markdown整形
│   ├── blog-article-generator/  # 記事生成
│   └── seo-optimizer/           # SEO最適化
├── hooks/                        # フック（将来拡張用）
│   └── README.md
├── scripts/                      # 外部スクリプト（将来拡張用）
│   └── README.md
├── commands/                     # スラッシュコマンド（将来拡張用）
│   └── README.md
├── mcp/                          # MCPサーバー（将来拡張用）
│   └── README.md
├── tests/                        # テスト
│   └── README.md
├── examples/                     # 使用例
│   └── README.md
├── docs/                         # 詳細ドキュメント
│   └── README.md
├── .gitignore
├── LICENSE
├── README.md
├── CONTRIBUTING.md              # コントリビューションガイド
├── CHANGELOG.md                 # 変更履歴
└── PUBLISH.md                   # 公開手順
```

---

## 🛠️ 技術仕様

- **プラグインタイプ**: 統合プラグイン（Agents + Skills）
- **バージョン**: 1.0.0
- **必要なツール**: WebSearch, Read, Write, Edit, Grep, Glob
- **対応モデル**: Claude Sonnet, Claude Opus
- **言語**: Markdown (プロンプトベース)
- **ライセンス**: MIT

---

## 🤝 コントリビューション

コントリビューションを歓迎します！詳細は [CONTRIBUTING.md](CONTRIBUTING.md) をご覧ください。

### 開発フロー

1. このリポジトリをフォーク
2. フィーチャーブランチを作成 (`git checkout -b feature/amazing-feature`)
3. 変更をコミット (`git commit -m 'Add amazing feature'`)
4. ブランチにプッシュ (`git push origin feature/amazing-feature`)
5. Pull Requestを作成

---

## 📝 ライセンス

このプロジェクトは [MIT License](LICENSE) の下でライセンスされています。

---

## 👤 作成者

**Claude Code User**

---

## 📮 サポート・バグ報告

- **Issues**: [GitHub Issues](https://github.com/YOUR_USERNAME/blog-writing-suite/issues)
- **Discussions**: [GitHub Discussions](https://github.com/YOUR_USERNAME/blog-writing-suite/discussions)
- **Email**: your-email@example.com

---

## 🔗 関連リンク

- [Claude Code 公式ドキュメント](https://docs.claude.com/claude-code)
- [プラグイン開発ガイド](https://docs.claude.com/claude-code/plugins)
- [MCP プロトコル仕様](https://modelcontextprotocol.io/)

---

## 📊 変更履歴

### v1.0.0 (2025-10-26)
- ✨ 初回リリース
- 🤖 3つのエージェントを統合
- 🛠️ 3つのスキルを統合
- 📄 完全なブログ記事執筆ワークフローを提供

詳細は [CHANGELOG.md](CHANGELOG.md) をご覧ください。

---

<p align="center">
  Made with ❤️ by Claude Code Community
</p>
