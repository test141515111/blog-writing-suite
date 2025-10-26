# プラグイン公開ガイド

このドキュメントでは、Blog Writing Suite Pluginを GitHubリポジトリとして公開し、Claude Code Marketplaceで配布可能にする手順を説明します。

---

## 📋 目次

1. [事前準備](#事前準備)
2. [GitHubリポジトリの作成](#githubリポジトリの作成)
3. [初回push](#初回push)
4. [リリースの作成](#リリースの作成)
5. [Claude Code Marketplaceへの登録](#claude-code-marketplaceへの登録)
6. [更新とメンテナンス](#更新とメンテナンス)

---

## 事前準備

### 必要なもの

- GitHubアカウント
- Git CLIインストール済み
- Claude Code CLIインストール済み

### 確認事項

- [ ] すべてのファイルが正しく配置されている
- [ ] README.mdに正確な情報が記載されている
- [ ] plugin.jsonに正しいメタデータが設定されている
- [ ] LICENSEファイルが含まれている
- [ ] .gitignoreが適切に設定されている

---

## GitHubリポジトリの作成

### ステップ1: GitHub上でリポジトリを作成

1. [GitHub](https://github.com)にログイン
2. 右上の「+」→「New repository」をクリック
3. リポジトリ情報を入力：
   - **Repository name**: `blog-writing-suite`
   - **Description**: `ブログ記事執筆のための統合Claude Codeプラグイン`
   - **Public** を選択（Marketplaceで配布するため）
   - **Initialize this repository**のチェックは**すべて外す**（ローカルに既存のファイルがあるため）
4. 「Create repository」をクリック

### ステップ2: 作成されたURLを確認

GitHubに表示される以下のURLをコピー：
```
https://github.com/YOUR_USERNAME/blog-writing-suite.git
```

---

## 初回push

### ステップ1: ローカルリポジトリの初期化

```bash
# プラグインディレクトリに移動
cd /path/to/your/project/.claude/plugins/blog-writing-suite

# Gitリポジトリを初期化
git init

# ファイルをステージング
git add .

# 初回コミット
git commit -m "feat: initial release v1.0.0

- Add 3 specialized agents (ExpertAnalyst, TechnicalWriter, CredibilityEnhancer)
- Add 3 skills (markdown-formatter, blog-article-generator, seo-optimizer)
- Add standard plugin structure (hooks, scripts, commands, mcp, tests, examples, docs)
- Add comprehensive documentation (README, CONTRIBUTING, PUBLISH, CHANGELOG)
"
```

### ステップ2: リモートリポジトリを追加

```bash
# GitHubリポジトリをリモートに追加
git remote add origin https://github.com/YOUR_USERNAME/blog-writing-suite.git

# リモートの確認
git remote -v
```

### ステップ3: pushを実行

```bash
# mainブランチにpush
git branch -M main
git push -u origin main
```

---

## リリースの作成

### ステップ1: タグを作成

```bash
# v1.0.0タグを作成
git tag -a v1.0.0 -m "Release v1.0.0

Initial release with 3 agents and 3 skills for comprehensive blog article writing workflow.
"

# タグをpush
git push origin v1.0.0
```

### ステップ2: GitHub Releaseを作成

1. GitHubリポジトリページで「Releases」タブをクリック
2. 「Create a new release」をクリック
3. 情報を入力：
   - **Tag**: `v1.0.0` （既存のタグを選択）
   - **Release title**: `v1.0.0 - Initial Release`
   - **Description**:
     ```markdown
     ## ✨ 初回リリース

     Blog Writing Suite Plugin v1.0.0をリリースしました！

     ### 主な機能

     #### エージェント（3つ）
     - 🤖 **ExpertAnalystAgent**: テーマ分析とアウトライン設計
     - 🤖 **TechnicalWriterAgent**: 本文執筆
     - 🤖 **CredibilityEnhancerAgent**: 信頼性強化

     #### スキル（3つ）
     - 🛠️ **markdown-formatter**: Markdown整形
     - 🛠️ **blog-article-generator**: 記事生成
     - 🛠️ **seo-optimizer**: SEO最適化

     ### インストール

     \`\`\`bash
     claude plugin install https://github.com/YOUR_USERNAME/blog-writing-suite
     \`\`\`

     ### ドキュメント

     詳細な使用方法は[README.md](https://github.com/YOUR_USERNAME/blog-writing-suite/blob/main/README.md)をご覧ください。
     ```
4. 「Publish release」をクリック

---

## Claude Code Marketplaceへの登録

### ステップ1: plugin.jsonのURLを更新

```bash
# plugin.jsonのrepository URLを実際のURLに更新
cd .claude-plugin
# エディタでplugin.jsonを開き、YOUR_USERNAMEを実際のユーザー名に置換
```

### ステップ2: Marketplace登録申請

Claude Code公式に連絡し、プラグインの登録を申請します。

**申請に必要な情報:**
- プラグイン名: `blog-writing-suite`
- GitHubリポジトリURL: `https://github.com/YOUR_USERNAME/blog-writing-suite`
- バージョン: `1.0.0`
- 短い説明: ブログ記事執筆のための統合プラグイン
- カテゴリ: Content Creation, Productivity

### ステップ3: 承認を待つ

通常、1-2週間でレビューと承認が行われます。

---

## 更新とメンテナンス

### バグ修正リリース（パッチ）

```bash
# 修正を実施
# ...

# コミット
git add .
git commit -m "fix: bug description"

# plugin.jsonのバージョンを更新（1.0.0 → 1.0.1）
# CHANGELOG.mdを更新

# タグを作成してpush
git tag -a v1.0.1 -m "Release v1.0.1: Bug fixes"
git push origin main
git push origin v1.0.1

# GitHub Releaseを作成
```

### 新機能リリース（マイナー）

```bash
# 新機能を実装
# ...

# plugin.jsonのバージョンを更新（1.0.0 → 1.1.0）
# CHANGELOG.mdを更新

# タグを作成してpush
git tag -a v1.1.0 -m "Release v1.1.0: New features"
git push origin main
git push origin v1.1.0

# GitHub Releaseを作成
```

### 破壊的変更（メジャー）

```bash
# 破壊的変更を実装
# ...

# plugin.jsonのバージョンを更新（1.0.0 → 2.0.0）
# CHANGELOG.mdを更新
# READMEにマイグレーションガイドを追加

# タグを作成してpush
git tag -a v2.0.0 -m "Release v2.0.0: Breaking changes"
git push origin main
git push origin v2.0.0

# GitHub Releaseを作成
```

---

## セマンティックバージョニング

プラグインのバージョン管理は[Semantic Versioning](https://semver.org/)に従います：

- **MAJOR** (1.0.0 → 2.0.0): 後方互換性のない変更
- **MINOR** (1.0.0 → 1.1.0): 後方互換性のある新機能
- **PATCH** (1.0.0 → 1.0.1): 後方互換性のあるバグ修正

---

## トラブルシューティング

### Qerror: remote origin already exists

```bash
# 既存のremoteを削除
git remote remove origin

# 再度追加
git remote add origin https://github.com/YOUR_USERNAME/blog-writing-suite.git
```

### Q: push時に認証エラー

```bash
# Personal Access Tokenを使用
git remote set-url origin https://YOUR_USERNAME:YOUR_TOKEN@github.com/YOUR_USERNAME/blog-writing-suite.git
```

### Q: plugin.jsonのURL更新を忘れた

```bash
# plugin.jsonを修正
# コミットしてpush
git add .claude-plugin/plugin.json
git commit -m "fix: update repository URLs in plugin.json"
git push origin main
```

---

## チェックリスト

公開前に以下を確認してください：

- [ ] README.mdのYOUR_USERNAMEを実際のユーザー名に置換
- [ ] plugin.jsonのURLを実際のURLに置換
- [ ] CHANGELOG.mdが最新
- [ ] すべてのリンクが正しく機能する
- [ ] ライセンス情報が正確
- [ ] .gitignoreが適切に設定されている
- [ ] 機密情報（APIキー等）が含まれていない

---

おめでとうございます！これであなたのプラグインが世界中で利用可能になります！🎉
