---
title: "Foundry Local"
description: "A local AI doc assistant that combines on-device inference with Foundry Local and grounded documentation retrieval from Learn MCP Server. No API keys needed."
categories:
  - Learning
tags:
  - Artificial intelligence
---

What if your AI assistant ran entirely on your device but still had access to up-to-date Microsoft docs?

![screenshot of Foundry Local + Learn MCP Server](/assets/images/2026-04-10-foundry-local.jpg)

I built a small app that combines Foundry Local (on-device inference with phi-4-mini) and Learn MCP Server (documentation retrieval). You ask a question, the local model calls a search tool, gets doc content from Learn, and synthesizes a grounded answer. No API keys, no cloud LLM costs.

```
User Question → Foundry Local (phi-4-mini) → Learn MCP Server → Grounded Answer
```

It's adapted from the Foundry Local tutorial-tool-calling sample, replacing the weather tool with a docs search tool. The key design choice: `tool_choice: required`, which means the model always searches before answering.

[Repo](https://github.com/pdebruin/learn-mcp-foundry-local)

[Discussion](https://github.com/MicrosoftDocs/mcp/discussions/151)

Thanks for reading! :-)
