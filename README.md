# relie-skills

Relie 的公开技能库，Codex 和 Claude Code 都可以使用。目前有两个技能：

| 技能 | 适合 | 需要 |
|---|---|---|
| **[relie-video-transcript](skills/relie-video-transcript/SKILL.md)** | 抖音、小红书、快手、B 站视频的口播逐字稿，以及点赞、评论、收藏、分享、播放量、评论内容等数据；单条或成百上千条批量 | TikHub 与阿里云百炼的 API Key |
| **[relie-getnote-transcript](skills/relie-getnote-transcript/SKILL.md)** | 微信公众号文章正文；没有上述 API Key 时，也可以通过 Get 笔记获取视频逐字稿 | 已登录的 Get 笔记账号 |

## relie-video-transcript

通过 TikHub 接口解析链接，再交给阿里云百炼 Paraformer 转写，全程由技能自带的 Python 脚本完成，不需要操作网页。支持批量和断点续跑，输出每条视频一个 Markdown 逐字稿（带时间点），外加 Excel / CSV 汇总表。

能拿到的数据（随解析一起返回，不额外计费）：

| 平台 | 点赞 | 评论数 | 收藏 | 分享 | 播放量 | 其他 |
|---|---|---|---|---|---|---|
| 抖音 | ✅ | ✅ | ✅ | ✅ | 需加 `--douyin-plays`（每条多一次调用） | 话题标签 |
| 小红书 | ✅ | ✅ | ✅ | ✅ | 平台不公开 | 话题标签 |
| 快手 | ✅ | ✅ | ✅ | ✅ | ✅ | 话题标签 |
| B 站 | ✅ | ✅ | ✅ | ✅ | ✅ | 投币、弹幕数 |

评论内容需要加 `--comments N`，按页额外计费。

### 准备

1. 安装 Python 3.9 以上，运行 `python -m pip install -r skills/relie-video-transcript/requirements.txt`。
2. 在 [TikHub](https://user.tikhub.io) 创建 API 令牌；在阿里云百炼 **华北2（北京）** 地域创建 API Key。
3. 把 `transcript.env.example` 复制到用户目录下的 `.relie/transcript.env`（Windows 为 `C:\Users\<用户名>\.relie\transcript.env`），填入两个 Key。Key 不要放进技能目录或本仓库。

费用参考（2026-10）：TikHub 抖音、快手、B 站每次调用 $0.001，小红书 $0.01；百炼按音频时长计费，每月有免费额度。以两家控制台为准。

## 安装

在 Codex 中说：

> 请安装这个 Skill：https://github.com/brotherbear2008/relie-skills/tree/main/skills/relie-video-transcript

也可以克隆本仓库，把 `skills/` 下需要的技能文件夹复制到：

- Codex：`~/.codex/skills/`
- Claude Code：`~/.claude/skills/`

安装后开始新的对话，例如发送：

> 帮我获取这个视频的逐字稿：<视频链接>

> 拿一下这几条视频的点赞、收藏和前 20 条评论：<链接1> <链接2>

> 把 links.txt 里的视频都转成逐字稿，先试跑 5 条

> 用 Get 笔记获取这篇公众号文章的正文：<公众号链接>

## 使用说明

- 两个技能都不包含账号、Cookie 或密钥。relie-video-transcript 的 Key 保存在你本机的配置文件里；relie-getnote-transcript 使用你自己已登录的 Get 笔记账号。
- 逐字稿来自语音识别，未经人工校对；视频配文、AI 总结不会冒充逐字稿。拿不到时会如实说明原因。
- relie-video-transcript 一次处理较多链接或开启评论抓取前，会先说明条数和费用。
- 只处理你指定的作品，不做整个账号的采集。逐字稿和评论供个人研究使用，转载请注意原作者版权。

本仓库采用 MIT License。
