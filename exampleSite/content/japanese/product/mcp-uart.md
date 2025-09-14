---
title: "MCP UARTサーバー"
banner:
  title: "UART‑pyAutoPort‑MCPサーバー"
  content: "pyautoportライブラリを使用したUART通信のMCP（Model Context Protocol）サーバーです。UARTポートやボーレートを簡単に設定し、コマンド送信や自動化ワークフローと統合できます。"
  image: "/images/product-mcp-uart.png"
  button:
    enable: true
    label: "GitHubで表示"
    link: "https://github.com/alroborol/mcp-uart"
features:
  - title: "柔軟なUART制御"
    image: "/images/product-mcp-uart-1.png"
    content: "MCPツールでUARTポートやボーレートを設定。タイムアウト付きでコマンド送信・応答受信が可能。"
    bulletpoints:
      - "UARTポートとボーレートを簡単設定。"
      - "コマンド送信と応答受信。"
      - "堅牢な通信のためのタイムアウト機能。"
    button:
      enable: false
      label: ""
      link: ""
  - title: "自動化統合"
    image: "/images/product-mcp-uart-2.png"
    content: "ZedやVS Codeなどのツールや自動化ワークフローと統合。"
    bulletpoints:
      - "ZedやVS CodeでMCPサーバーを追加。"
      - "自動化スクリプトとの連携。"
    button:
      enable: false
      label: ""
      link: ""
usage: |
  ## 使用方法
  
  ### Zedでの接続
  1. スクリプトをダウンロード: uart-pyautoport-mcp.py
  2. uvをインストール: https://docs.astral.sh/uv/getting-started/installation/
  3. 設定テンプレートを使ってVS CodeやZedにMCPサーバーを追加:
  
      {
        "uart-mcp-server": {
          "command": {
            "path": "uv",
            "args": ["run", "path/to/uart-pyautoport-mcp"],
            "env": {}
          }
        }
      }
  
  「path/to/uart-pyautoport-mcp」を実際のスクリプトパスに置き換えてください。
  
  ### 直接MCPサーバー起動
  実行:
  
      python uart-pyautoport-mcp.py
  
  ### 必要要件
  - Python 3.8+
  - pyautoport
  - mcp[cli]
  
  ### ライセンス
  MIT
  
  ### リンク
  - [GitHubリポジトリ](https://github.com/alroborol/mcp-uart)
---