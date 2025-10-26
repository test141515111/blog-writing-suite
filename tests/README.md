# Tests

このディレクトリは、プラグインのテストコードを配置する場所です。

## テストの種類

### 1. エージェントテスト
エージェントが正しく動作するかをテストします。

```
tests/
└── agents/
    ├── test_expert_analyst.py
    ├── test_technical_writer.py
    └── test_credibility_enhancer.py
```

### 2. スキルテスト
スキルが正しく動作するかをテストします。

```
tests/
└── skills/
    ├── test_markdown_formatter.py
    ├── test_blog_article_generator.py
    └── test_seo_optimizer.py
```

### 3. 統合テスト
エージェントとスキルを組み合わせた全体ワークフローをテストします。

```
tests/
└── integration/
    └── test_full_blog_workflow.py
```

## テスト実行方法

```bash
# すべてのテストを実行
pytest tests/

# 特定のテストを実行
pytest tests/agents/test_expert_analyst.py

# カバレッジ付きで実行
pytest --cov=. tests/
```

## 現在の状態

現在、このプラグインではテストコードを実装していません。将来の品質保証のために空フォルダとして準備されています。

テストを追加する際は、以下の依存関係が必要です：

```txt
pytest>=7.0.0
pytest-cov>=4.0.0
pytest-mock>=3.10.0
```
