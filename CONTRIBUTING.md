# Contributing to Blog Writing Suite Plugin

まず、このプロジェクトへのコントリビューションを検討していただき、ありがとうございます！

このドキュメントでは、プロジェクトへの貢献方法について説明します。

---

## 📋 目次

- [行動規範](#行動規範)
- [開発環境のセットアップ](#開発環境のセットアップ)
- [コントリビューションの種類](#コントリビューションの種類)
- [Pull Requestのプロセス](#pull-requestのプロセス)
- [コーディング規約](#コーディング規約)
- [コミットメッセージ規約](#コミットメッセージ規約)
- [質問とサポート](#質問とサポート)

---

## 行動規範

このプロジェクトは、すべての参加者が互いに尊重し合うコミュニティです。以下の行動を期待します：

- 他の人々に対して敬意を持って接する
- 建設的なフィードバックを提供する
- プロジェクトの目標とビジョンを尊重する
- オープンで透明性のあるコミュニケーション

---

## 開発環境のセットアップ

### 前提条件

- Claude Code CLI がインストールされていること
- Gitがインストールされていること
- Markdownエディタ（VSCode推奨）

### セットアップ手順

```bash
# 1. リポジトリをフォーク
# GitHubでForkボタンをクリック

# 2. ローカルにクローン
git clone https://github.com/YOUR_USERNAME/blog-writing-suite.git
cd blog-writing-suite

# 3. 上流リポジトリを追加
git remote add upstream https://github.com/ORIGINAL_OWNER/blog-writing-suite.git

# 4. Claude Codeプロジェクトの.claude/pluginsにシンボリックリンク
ln -s $(pwd) /path/to/your/claude/project/.claude/plugins/blog-writing-suite

# 5. 動作確認
claude
# → @expert-analyst, @technical-writer, @credibility-enhancer が使用可能
```

---

## コントリビューションの種類

### 1. バグ報告

バグを発見した場合は、以下の情報を含めてIssueを作成してください：

- **バグの説明**: 何が起こったか
- **再現手順**: 問題を再現する方法
- **期待される動作**: 何が起こるべきか
- **実際の動作**: 実際に何が起こったか
- **環境**: Claude Codeバージョン、OS、モデル

### 2. 機能提案

新しい機能を提案する場合は、以下を含めてください：

- **機能の説明**: 何を追加したいか
- **動機**: なぜこの機能が必要か
- **使用例**: どのように使用するか
- **代替案**: 検討した他の方法

### 3. ドキュメント改善

- タイポの修正
- 説明の明確化
- 使用例の追加
- 翻訳

### 4. コード改善

- エージェントの改善
- スキルの改善
- 新しいエージェント/スキルの追加
- テストの追加

---

## Pull Requestのプロセス

### 1. ブランチを作成

```bash
# mainブランチから最新を取得
git checkout main
git pull upstream main

# 新しいブランチを作成
git checkout -b feature/your-feature-name
# または
git checkout -b fix/bug-description
```

### 2. 変更を加える

- コードを編集
- 必要に応じてテストを追加
- ドキュメントを更新

### 3. コミット

```bash
git add .
git commit -m "feat: add new feature"
```

### 4. プッシュ

```bash
git push origin feature/your-feature-name
```

### 5. Pull Requestを作成

GitHubで「New Pull Request」ボタンをクリックし、以下を記入：

- **タイトル**: 変更内容の簡潔な説明
- **説明**: 変更の詳細、動機、影響
- **関連Issue**: `Closes #123` のように記載

---

## コーディング規約

### Markdownフォーマット

- 見出しは `#` を使用（`===` は使わない）
- リストは `*` または `-` で統一
- コードブロックは言語指定を必ず付ける
- 1行は80文字以内を推奨

### エージェント/スキルの構造

```markdown
---
name: agent-name
description: エージェントの説明
tools: WebSearch, Read, Write
model: sonnet
---

# Agent Name

## あなたの役割
...

## 実行手順
...
```

### ファイル命名規則

- エージェント: `kebab-case.md`（例: `expert-analyst.md`）
- スキル: `kebab-case/SKILL.md`（例: `markdown-formatter/SKILL.md`）
- ドキュメント: `UPPERCASE.md`（例: `README.md`, `CONTRIBUTING.md`）

---

## コミットメッセージ規約

Conventional Commitsに従います：

```
<type>(<scope>): <subject>

<body>

<footer>
```

### Type

- `feat`: 新機能
- `fix`: バグ修正
- `docs`: ドキュメントのみの変更
- `style`: フォーマットの変更（ロジック変更なし）
- `refactor`: リファクタリング
- `test`: テストの追加・修正
- `chore`: ビルドプロセス、ツールの変更

### 例

```bash
feat(agent): add new SEO analysis agent

Add a new agent for advanced SEO analysis including:
- Keyword density calculation
- Readability score
- Meta tag validation

Closes #42
```

---

## 質問とサポート

### Issuesで質問

使い方がわからない、動作しないなどの質問は、GitHub Issuesで質問してください。

### Discussionsで議論

新機能のアイデアや設計について議論したい場合は、GitHub Discussionsを使用してください。

### 直接連絡

緊急の問題や機密情報については、メールでご連絡ください：
- Email: your-email@example.com

---

## レビュープロセス

Pull Requestは以下の基準でレビューされます：

1. **機能性**: 意図した通りに動作するか
2. **品質**: コードが読みやすく保守しやすいか
3. **ドキュメント**: 適切に文書化されているか
4. **テスト**: 必要なテストが含まれているか
5. **互換性**: 既存の機能を壊していないか

通常、1-3日以内にレビューが行われます。

---

## ライセンス

コントリビューションは、プロジェクトのMITライセンスの下で公開されます。

---

ご協力ありがとうございます！🎉
