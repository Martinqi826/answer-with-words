# answer-with-words · 词汇回答

**先看关键词，需要时再展开。**  
**Keywords first. Expand on request.**

一个让 AI 通常用 **1–7 个关键词或短词组**回答问题的 Agent Skill。显式启用，随时退出。

An Agent Skill for replies in **1–7 keywords or short phrases**. Enable it explicitly; ask to expand when you need more detail.

[中文](#中文) · [English](#english) · [完整规则 / Skill](skills/answer-with-words/SKILL.md)

![普通表达与词汇表达的中英文对比示意 / Prose and keyword example](comparison.png)

## 中文

### 适合做什么？

- **头脑风暴**：先列出值得思考的方向。
- **提炼关键因素**：把熟悉的问题压缩为一组提示词。
- **词汇问答游戏**：限制词数，观察不同问题的核心答案。

这是回答风格规则。需要推理、证据或操作步骤时，直接要求展开；创建文件、编写代码、执行操作等任务仍需实际完成。

### 三组效果示意

以下是为说明表达方式编写的例子，**不是模型对照实验、实测截图或性能评测**。

| 问题 | 普通表达（示意） | 词汇表达（示意） |
| --- | --- | --- |
| 人生的意义是什么？ | 可以从体验生活、建立爱的联结，以及创造有价值的事物中寻找意义。 | 体验、爱、创造 |
| 如何提高阅读效率？ | 阅读前明确目标，带着问题选择重点内容；读后用主动回忆与间隔复习巩固。 | 明确目标、带着问题读、重点精读、主动回忆、间隔复习 |
| 如何做好 UGC 玩法平台？ | 围绕用户需求，提供创作工具和内容供给，再做好分发、留存、激励与治理。 | 需求、工具、内容、分发、留存、激励、治理 |

### 安装

准备好 **Node.js 22.20 或更高版本、npm 和 Git**，在希望使用该 Skill 的项目目录执行：

```bash
npx skills add Martinqi826/answer-with-words --skill answer-with-words
```

按提示选择客户端与安装方式。默认是当前项目范围；不需要创建本项目的账号或提供 API Key。

也可以明确指定客户端，例如 Codex：

```bash
npx skills add Martinqi826/answer-with-words --skill answer-with-words -a codex --copy -y
```

Claude Code 用户将 `codex` 换成 `claude-code`。`--copy` 使用文件副本，`-y` 跳过安装确认；希望自行选择时可去掉这些选项。

安装范围与当前验证结果见 [INSTALLATION.md](INSTALLATION.md)。CLI 的完整选项见 [官方文档](https://github.com/vercel-labs/skills/blob/main/docs/commands.md)。

### 启用、指定数量、退出

在已加载该 Skill 的客户端中输入：

```text
使用 answer-with-words，仅用词汇回答接下来的问题。
```

随后直接提问，也可以指定数量：

```text
只用三个词回答：团队协作最重要的是什么？
```

需要详细回答时：

```text
展开解释刚才的答案。
```

或明确退出：

```text
退出词汇回答模式，正常回答。
```

### 行为规则

- 使用用户的语言；通常一行、1–7 项。中文用顿号，英文用逗号。
- 用户指定词数时遵循要求；不添加开场白、标题、解释或总结。
- 只在明确要求词汇回答、关键词回答或进入词汇问答游戏时启用；普通“简洁回答”不触发。
- 保留必要限定。信息不足就明确表达“不知道”或“信息不足”。
- “展开”“解释”“正常回答”会切换表达方式；需要时可重新启用。
- 事实核查、必要引用、安全要求和实际任务交付优先于词汇格式。

### 为什么做成 Skill？

直接写一句“只给关键词”也能尝试这种风格。Skill 将触发条件、词数、退出方式和边界保存为可复用的规则，便于在支持 Skills 的工具中重复使用。实际表现仍取决于模型、客户端和上下文；本项目不承诺准确率、速度或费用改善。

### 反馈与支持

欢迎在 [Issues](https://github.com/Martinqi826/answer-with-words/issues) 中附上问题、实际回答、预期回答，以及客户端和模型名称。请先移除私人信息。

如果它对你有用，欢迎 **Star**。可直接使用的介绍文案见 [PROMOTION.md](PROMOTION.md)。

## English

### What is it for?

- **Brainstorming**: start with a small set of directions.
- **Extracting key factors**: turn a familiar topic into compact prompts.
- **Word-answer games**: answer within a requested number of words or phrases.

This is a response-style skill. Ask for an explanation when reasoning, evidence, or steps matter. Requests to write code, create files, or perform actions still require actual completion.

### Three illustrative comparisons

These are authored examples of the format, **not model comparisons, actual screenshots, or performance benchmarks**.

| Question | Prose example | Keyword example |
| --- | --- | --- |
| What gives life meaning? | Meaning can come from experiencing life, building loving connections, and creating something valuable. | Experience, love, creation |
| How can I read more effectively? | Set a goal, read with questions, focus on relevant sections, then use active recall and spaced review. | Goals, questions, focused reading, active recall, spaced review |
| How do I build a UGC game platform? | Understand demand, support creation and content supply, then improve discovery, retention, incentives, and governance. | Demand, tools, content, discovery, retention, incentives, governance |

### Install

You need **Node.js 22.20+**, npm, and Git. Run this in the project where you want to use the skill:

```bash
npx skills add Martinqi826/answer-with-words --skill answer-with-words
```

Follow the prompts to choose your agent and installation method. Installation is project-scoped by default. The skill itself needs no account or API key; your agent's own requirements still apply.

To target Codex explicitly:

```bash
npx skills add Martinqi826/answer-with-words --skill answer-with-words -a codex --copy -y
```

For Claude Code, replace `codex` with `claude-code`. `--copy` installs file copies; `-y` skips confirmation. Omit these options if you prefer to choose interactively.

See [INSTALLATION.md](INSTALLATION.md) for verification scope and results, and the [official CLI documentation](https://github.com/vercel-labs/skills/blob/main/docs/commands.md) for all options.

### Use

Once the skill is loaded, ask:

```text
Use answer-with-words. Answer the next questions with keywords only.
```

You can request a count:

```text
Exactly three words: what matters most in teamwork?
```

To return to a normal response:

```text
Exit keyword mode and explain the previous answer.
```

### Rules and limits

- Use the user's language, usually one line with 1–7 words or short phrases.
- Follow an explicit item count. Skip introductions, headings, and explanations while the mode is active.
- Enable only for explicit word-only or keyword requests; a generic request for brevity does not activate it.
- Preserve essential qualifications and uncertainty. Ask a short clarification only when necessary.
- Requests to expand, explain, or answer normally change the response style.
- Verification, required citations, safety, and actual task completion take precedence over the format.

You can also try the style with a plain prompt. This skill packages the activation, count, exit, and boundary rules for reuse. Results depend on the model, client, and context; no accuracy, speed, or cost improvement is claimed.

### Feedback

Open an [issue](https://github.com/Martinqi826/answer-with-words/issues) with your prompt, actual and expected replies, agent, and model. Remove private information before posting. If the skill is useful, a **Star** helps others discover it.

### Repository

| Path | Purpose |
| --- | --- |
| `skills/answer-with-words/SKILL.md` | Complete skill instructions |
| `skills/answer-with-words/agents/openai.yaml` | Display name and default prompt |
| `INSTALLATION.md` | Installation verification and its limits |
| `comparison.png` | Bilingual illustrative comparison |
| `PROMOTION.md` | Ready-to-use launch copy |
