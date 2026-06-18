# Codex Code Simplifier

中文 | [English](#english)

一个面向 Codex 的代码简化插件市场，提供 `code-simplifier` 工作流，用于清理最近修改的代码，同时保持行为不变。

## 在 Codex App 中安装

打开 **Plugins** -> **Add marketplace**，填写：

```text
Git reference: yidasanqian/codex-code-simplifier@main
Precise path: .agents/plugins
```

Codex 加载市场后，安装 `Code Simplifier` 插件。

## 如何使用

这个插件不是 MCP 工具，也不是 slash command。它提供的是一套代码简化 workflow，所以使用时需要带上目标。

推荐写法：

```text
@Code Simplifier 简化当前未提交改动，保持行为不变
```

也可以直接说：

```text
Use code-simplifier on my recent changes.
```

工作流会优先关注当前会话或最近修改的文件，遵循项目里的 `AGENTS.md`，避免无关重构，并在可行时运行相关验证。

## 包含内容

- `plugins/code-simplifier/skills/code-simplifier/SKILL.md`：可安装的 Codex skill。
- `plugins/code-simplifier/agents/code-simplifier.md`：面向支持 plugin-level agents 的 Codex surface。
- `.codex/agents/code-simplifier.toml`：可选的项目级 subagent 模板；需要时可以复制到目标项目的 `.codex/agents/` 目录。

## 仓库结构

```text
.agents/plugins/marketplace.json
plugins/code-simplifier/.codex-plugin/plugin.json
plugins/code-simplifier/skills/code-simplifier/SKILL.md
plugins/code-simplifier/agents/code-simplifier.md
.codex/agents/code-simplifier.toml
```

## English

A Codex plugin marketplace that packages a `code-simplifier` workflow for cleaning up recently modified code without changing behavior.

## Install In Codex App

Open **Plugins** -> **Add marketplace**, then use:

```text
Git reference: yidasanqian/codex-code-simplifier@main
Precise path: .agents/plugins
```

Install the `code-simplifier` plugin from the marketplace after Codex loads it.

## Use

This plugin provides workflow instructions, not an MCP tool or slash command. Mention it with a concrete target:

```text
@Code Simplifier simplify my uncommitted changes without changing behavior
```

Or ask directly:

```text
Use code-simplifier on my recent changes.
```

The workflow focuses on files changed in the current session, preserves behavior, follows `AGENTS.md`, and verifies the affected surface where possible.

## What It Includes

- `plugins/code-simplifier/skills/code-simplifier/SKILL.md`: installable Codex skill.
- `plugins/code-simplifier/agents/code-simplifier.md`: plugin-level agent definition for Codex surfaces that support plugin agents.
- `.codex/agents/code-simplifier.toml`: optional project-level subagent template. Copy this file into a project's `.codex/agents/` directory if you want to use it as a custom subagent.

## Repository Layout

```text
.agents/plugins/marketplace.json
plugins/code-simplifier/.codex-plugin/plugin.json
plugins/code-simplifier/skills/code-simplifier/SKILL.md
plugins/code-simplifier/agents/code-simplifier.md
.codex/agents/code-simplifier.toml
```
