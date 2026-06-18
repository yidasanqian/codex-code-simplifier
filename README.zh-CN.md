# Codex Code Simplifier

简体中文 | [English](README.md)

一个面向 Codex 的代码简化插件市场，提供 `code-simplifier` 工作流，用于清理最近修改的代码，同时保持行为不变。

## 在 Codex App 中安装

打开 **Plugins** -> **Add marketplace**，填写：

```text
Git reference: yidasanqian/codex-code-simplifier@main
Precise path: .agents/plugins
```

Codex 加载市场后，安装 `Code Simplifier` 插件。

## 如何使用

通过 Codex 的 slash command 选择器使用。输入 `/code`，选择 **Code Simplifier**，然后补上具体目标：

![Code Simplifier slash command](docs/images/codex-slash-code-simplifier.png)

推荐写法：

```text
/code 简化当前未提交改动，保持行为不变
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
