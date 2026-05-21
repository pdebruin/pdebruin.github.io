---
title: "Notepadmin"
description: "Windows Notepad got rich text, AI features, and a vulnerability. So I built a cross-platform plain-text editor with GitHub Copilot CLI, C#, .NET 10, and Avalonia UI."
categories:
  - Learning
tags:
  - Artificial intelligence
---

Windows Notepad has been my go-to tool for stripping formatting. Paste anything in, copy it back out, clean plain text. It's the one app I trust to not add anything.

Then Notepad got rich text formatting. Bold, italic, tables, headings, images. It also got AI writing features, and a cve.

I also wanted to try building a cross-platform app with GitHub Copilot CLI. So I built Notepadmin, a minimal plain-text editor that's a marriage of classic Notepad (text only, no formatting!) and gedit. Built with C#, .NET 10, and Avalonia UI, it always pastes as plain text and runs on both Windows and Linux.

![Notepadmin on Ubuntu](https://raw.githubusercontent.com/pdebruin/notepadmin/main/screen-notepadmin-ubu.png)

The entire app was built through GitHub Copilot CLI, from requirements to a working cross-platform binary with CI/CD releasing to GitHub.

[Repo](https://github.com/pdebruin/notepadmin)

Thanks for reading! :-)
