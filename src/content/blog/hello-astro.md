---
title: "第一篇 Astro 博客"
description: "这是新博客的示例文章，用来确认 Markdown 写作和 GitHub Pages 发布流程。"
pubDate: 2026-06-16
tags: ["Astro", "Markdown"]
---

这是新博客的第一篇示例文章。

以后新增文章，只需要在 `src/content/blog/` 目录下新建一个 Markdown 文件：

```text
src/content/blog/my-new-post.md
```

文章开头保留 frontmatter：

```md
---
title: "文章标题"
description: "一句话摘要"
pubDate: 2026-06-16
tags: ["tag"]
---
```

然后正常写 Markdown 正文即可。
