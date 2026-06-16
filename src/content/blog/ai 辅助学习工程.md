---
title: ai 辅助学习工程
description: ai 辅助学习工程。
pubDate: 2026-06-17
tags:
  - study
  - agent
---
为了恶补工程能力，我决定从头学习一些工程的内容。我想要试试 ai 是否能够帮助加速这个过程。

可以使用 AGENT.md 或 CLAUDE.md 来告诉 agent，目标不是“快速完成任务”，而是“在完成项目的同时训练工程能力”。
可以用这个：

```markdown
# AI Collaboration Rules

This project is a learning project. The primary goal is to improve my engineering ability, not to finish features as fast as possible.

## Role of AI

AI should act as a mentor, reviewer, and pair-programming coach.

AI may:
- Explain concepts and existing code.
- Help compare design options.
- Review my design before implementation.
- Generate small, localized code snippets.
- Suggest tests and debugging strategies.
- Ask me questions to check my understanding.

AI should not:
- Implement an entire feature end-to-end without my design first.
- Hide complexity behind unexplained code.
- Introduce frameworks or abstractions without explaining why.
- Skip tests, error handling, or documentation.
- Optimize for speed over learning.

## Required Workflow

For every non-trivial feature:

1. I write a short design first:
   - What problem does this solve?
   - What are the inputs and outputs?
   - What data models are involved?
   - What can fail?
   - How will I test it?

2. AI reviews the design:
   - Point out missing cases.
   - Ask clarifying questions.
   - Suggest alternatives.

3. Implementation is done in small steps:
   - Prefer one module or one function at a time.
   - Explain each change.
   - Avoid large unexplained code dumps.

4. After implementation:
   - Write or suggest tests.
   - Explain how to manually verify the feature.
   - Summarize what I should understand.

## Response Style

When I ask for help, prefer this structure:

1. First ask what I think, if my design is missing.
2. Then give hints or a plan.
3. Only provide code after the design is clear.
4. Explain the important parts of the code.
5. End with 2-3 questions I should be able to answer.

## Learning Priority

If there is a conflict between finishing quickly and helping me learn, choose helping me learn.
```

在使用 AI 时，可以这样来表达：

```text
1. 用户提交 username/password
2. 后端查 MySQL
3. 校验密码
4. 生成 JWT
5. 返回 token

请你先 review 这个设计，不要直接写代码。指出我遗漏的边界情况、表设计问题和测试点。
```

或者：
```text
请你像面试官一样追问我这个登录模块。
```

可以保留这些文档：

```text
AGENTS.md                  # AI 协作规则
docs/design/               # 每个模块的设计草稿
docs/reviews/              # 每周复盘、bug 记录、AI 使用记录
```

如果完全不懂，也可以这样问：

```text
我现在几乎没有工程设计经验。我想实现“提交代码并返回判题结果”功能。

请你不要直接给完整设计和代码。请你一步一步引导我：
1. 先问我 3 个必须思考的问题；
2. 等我回答后，再指出我的回答哪里不完整；
3. 最后给一个最小可行设计。
```

或者

```text
请你把这个功能拆成 5 个小问题，让我逐个回答。我的回答可能很幼稚，请你纠正我。
```

重点是要把不理解的地方完完全全地记录下来，或者搞明白，并且不要随便接受AI 替我实现的暂时做不到的复杂部分。

流程可以是：
```text
我不会 -> 写下我哪里不会 -> 让 AI 引导 -> 我改写 -> 再实现
```

暂定是这样的流程。之后实际用过之后可以看看效果如何。


关于 AI 写完代码之后 review 不动的情况，原则是不需要“比 AI 会”，而是需要建立一个review checklist。

AI 虽然会写，但是我是要对代码负责的那个人，AI 有责任向我解释他写的代码。

```text
1. 这个改动解决了什么问题？
2. 改了哪些文件？
3. 每个文件的职责是什么？
4. 入口函数在哪里？
5. 数据流是什么？
6. 哪些情况会失败？
7. 怎么测试？
8. 有没有多余抽象？
9. 有没有安全/并发/数据一致性风险？
10. 如果出 bug，我该看哪段日志？
```
