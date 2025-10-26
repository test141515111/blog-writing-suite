# MCP (Model Context Protocol)

このディレクトリは、MCPサーバー（Model Context Protocol Server）を配置する場所です。

## MCPサーバーとは？

MCPサーバーは、Claude Codeに新しいツール（関数）を追加するためのサーバープログラムです。JSON-RPC 2.0プロトコルで通信します。

## 使用例

将来、以下のようなMCPサーバーを追加する予定があります：

```
mcp/
├── seo-api-server.py          # SEO分析API MCPサーバー
├── content-db-server.py       # コンテンツDB MCPサーバー
├── .mcp.json                  # MCP設定ファイル
└── requirements.txt           # Python依存関係
```

### MCPサーバーの実装例

```python
#!/usr/bin/env python3
import json
import sys

def tools_list():
    """利用可能なツール一覧を返す"""
    return {
        "tools": [
            {
                "name": "analyze_seo",
                "description": "記事のSEOスコアを分析",
                "inputSchema": {
                    "type": "object",
                    "properties": {
                        "content": {"type": "string"}
                    }
                }
            }
        ]
    }

# JSON-RPC 2.0ハンドラー
# ...
```

## 現在の状態

現在、このプラグインではMCPサーバーを使用していません。すべての機能はClaude Codeの組み込みツールで実装されています。

MCPサーバーが必要になるのは、外部API（Google Trends、Ahrefs、Semrushなど）をリアルタイムで呼び出す機能を追加する場合です。
