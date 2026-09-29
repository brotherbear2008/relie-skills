# relie-skills

Relie 的公开 Codex 技能库。目前只提供一个技能：**[relie-getnote-transcript](skills/relie-getnote-transcript/SKILL.md)**。

把抖音、小红书或 B 站的**具体视频链接**发给 Codex，它会通过已登录的 Get 笔记（现称「得到大脑」）导入链接，读取「链接原文」并把取得的口播逐字稿交给你。Get 笔记的[官方说明](https://doc.biji.com/docs/GfPqwZfDRibB44kXvmvcQBRDngd)列出了这三类视频链接。

## 安装

在 Codex 中说：

> 请安装这个 Skill：https://github.com/brotherbear2008/relie-skills/tree/main/skills/relie-getnote-transcript

也可以克隆本仓库，将 `skills/relie-getnote-transcript` 文件夹复制到 `~/.codex/skills/`。安装后开始新的对话，例如发送「帮我获取这个视频的逐字稿：<视频链接>」。

## 使用说明

- 需要你自己可正常使用的 Get 笔记账号；这个 Skill 是供 AI 助手执行的流程说明，不是免登录下载器。
- 逐字稿来自 Get 笔记的原文入口。AI 总结、视频发布配文或图片文字不会冒充口播逐字稿。
- 某条链接如果正在处理、不受支持或只生成了部分内容，会如实说明，不承诺每条视频都能取得完整逐字稿。
- 技能不包含账号、Cookie、密钥或个人资料，也不下载视频文件。

本仓库采用 MIT License。
