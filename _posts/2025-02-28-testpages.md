# 文件路径：_posts/2024-02-20-welcome.md
---
layout: post
title: "我的第一篇技术文章"
date: 2024-02-20 15:00:00 +0800
categories: [技术, 教程]
tags: [github, jekyll]  # 标签系统
math: true               # 支持LaTeX公式
mermaid: true            # 支持流程图
---
## 欢迎来到我的技术博客

### 代码示例
```python
def fibonacci(n):
    a, b = 0, 1
    for _ in range(n):
        yield a
        a, b = b, a + b

print(list(fibonacci(10)))  # [0, 1, 1, 2, 3, 5, 8, 13, 21, 34]


