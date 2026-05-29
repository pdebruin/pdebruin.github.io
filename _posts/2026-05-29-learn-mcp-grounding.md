---
title: "Grounding agents in Microsoft Learn"
description: "A concrete test of the added value of connecting a coding agent to Learn MCP Server"
categories:
  - Learning
tags:
  - Artificial intelligence
---

Agents are good at writing code. They just don't know which API shipped last month.

I wrote about this on the Microsoft Developer Blog, with a test you can reproduce. Ask a coding agent to deploy Azure AI Foundry and it reaches for what used to be the right answer. It hits a dependency crash, spends fifteen tool calls debugging, and still produces a script targeting a deprecated API. Same prompt, same model, but with Learn MCP Server connected: the agent checks the docs first, finds the current surface, and delivers a working deployment on the first try.

![Blog teaser](/assets/images/2026-05-29-learn-mcp-grounding.jpg)

That is the whole point of grounding. Learn MCP Server gives any MCP-compatible agent direct access to current Microsoft documentation. For GitHub Copilot CLI:

```
/plugin install microsoftdocs/mcp
/restart
```

[Read the full post](https://developer.microsoft.com/blog/improve-your-agentic-developer-tools-by-grounding-in-microsoft-learn)

Thanks for reading! :-)
