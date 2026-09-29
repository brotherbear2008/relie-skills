# relie-skills

Relie 的公开 Codex 技能库。每个技能独立存放，可按需安装。

| 技能 | 用途 |
| --- | --- |
| [`douyin-copy`](skills/douyin-copy/SKILL.md) | 整理抖音作品的发布配文、口播原文、公开数据与评论样本 |
| [`xiaohongshu-copy`](skills/xiaohongshu-copy/SKILL.md) | 整理小红书笔记正文、图片文字与视频口播，并标明来源 |
| [`getnote-transcript`](skills/getnote-transcript/SKILL.md) | 从已授权的 Get 笔记页面读取和核验「链接原文」 |
| [`copy-breakdown`](skills/copy-breakdown/SKILL.md) | 按原文逐段标注功能、可替换材料和整体叙事结构 |

这些技能是供 AI 助手遵循的工作流程，不提供绕过登录或自动获取任意平台全文的接口。口播原文、发布配文和 AI 总结会分开标注；无法取得的内容保持未取得状态。

## 安装

在 Codex 中提供这个仓库的技能目录链接，并请它安装需要的技能。例如：

> 请安装 `https://github.com/brotherbear2008/relie-skills/tree/main/skills/douyin-copy` 里的 Codex skill。

也可以克隆仓库，将所需的 `skills/<技能名>` 文件夹复制到 `~/.codex/skills/`。安装后开始新的对话即可使用。每个文件夹都包含独立的 `SKILL.md`。

## 使用边界

- 只处理有权访问的内容；遵守来源网站的正常登录和访问流程。
- 保留原始链接、采集时间和内容状态，区分来源事实与分析判断。
- 分享或复刻文案时尊重原作者；技能不包含私人账号、Cookies、密钥或个人数据。

欢迎通过 Issue 提出改进建议。
