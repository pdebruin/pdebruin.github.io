---
title: "docs skill"
description: "A GitHub Copilot skill that analyzes a codebase and generates a browsable documentation site — built for the Afterburner challenge."
categories:
  - Learning
tags:
  - Artificial intelligence
---

The Afterburner challenge got me thinking: what's a skill that would be useful across any repo?

Generate-documentation is a GitHub Copilot skill that analyzes a codebase and produces a full docs site. It follows a 5-step workflow: map the territory, identify key components, generate documentation, configure mkdocs, and run quality checks. Output is a browsable docs/ directory with an mkdocs.yml.

The interesting design choice: when existing docs are present, it fills gaps without touching what's already there. No overwrites, no merge conflicts — it respects human-written content and only adds what's missing.

Tested against 5 repos of different sizes and types. Token usage scales with repo complexity, not repo size.

[Repo](https://github.com/pdebruin/docs-skill)

![screenshot of generate documentation skill](/assets/images/2026-05-22-docs-skill.jpg)

Thanks for reading! :-)
