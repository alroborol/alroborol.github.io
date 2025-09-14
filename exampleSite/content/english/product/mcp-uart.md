---
title: "MCP UART Server"
banner:
  title: "UART‑pyAutoPort‑MCP Server"
  content: "An MCP (Model Context Protocol) server for UART communication using the pyautoport library. Easily set UART port and baudrate, send commands, and integrate with automation workflows."
  image: "/images/product-mcp-uart.png"
  button:
    enable: true
    label: "View on GitHub"
    link: "https://github.com/alroborol/mcp-uart"
features:
  - title: "Flexible UART Control"
    image: "/images/product-mcp-uart-1.png"
    content: "Set UART port and baudrate via MCP tool. Write commands and read responses with timeout."
    bulletpoints:
      - "Configure UART port and baudrate easily."
      - "Send commands and receive responses."
      - "Timeout support for robust communication."
    button:
      enable: false
      label: ""
      link: ""
  - title: "Automation Integration"
    image: "/images/product-mcp-uart-2.png"
    content: "Integrate with automation workflows and tools like Zed or VS Code."
    bulletpoints:
      - "Add MCP server in Zed or VS Code."
      - "Use with automation scripts."
    button:
      enable: false
      label: ""
      link: ""
usage: |
  ## Usage
  
  ### Connect in Zed
  1. Download the script: uart-pyautoport-mcp.py
  2. Install uv: https://docs.astral.sh/uv/getting-started/installation/
  3. Add MCP server in VS Code or Zed using the configuration template:
  
      {
        "uart-mcp-server": {
          "command": {
            "path": "uv",
            "args": ["run", "path/to/uart-pyautoport-mcp"],
            "env": {}
          }
        }
      }
  
  Replace "path/to/uart-pyautoport-mcp" with the actual path to your script.
  
  ### Direct MCP Server
  Run:
  
      python uart-pyautoport-mcp.py
  
  ### Requirements
  - Python 3.8+
  - pyautoport
  - mcp[cli]
  
  ### License
  MIT
  
  ### Links
  - [GitHub Repository](https://github.com/alroborol/mcp-uart)
---
