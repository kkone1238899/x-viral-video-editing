# 视听剪辑技巧

> 剪辑太慢赶不上热点？这个库收集 AI 剪辑和自动套剪的方法，每条都写清楚能帮你解决什么、怎么用它搞钱。
>
> A curated collection of editing techniques prompts & skills for viral short videos, gathered from practitioners sharing on X.
> 
> Each entry answers: what problem it solves (and who it's for), how to use it step by step, and how to make money with it.
> 
> Star counts verified via GitHub API on 2026-10-12. Continuously updated.

## 条目

### YumCut

**核心提炼**
- 解决什么问题：想批量做竖屏短视频但不会剪、没时间剪——一句话想法直接变成可发布的 9:16 成片（脚本、配音、画面、字幕自动拼好）。
- 核心用法（4 步）：1) 自部署或直接用托管版 → 2) 输入想法/主题 → 3) 系统自动生成脚本→配音→画面→字幕 → 4) 导出成片发 TikTok/Reels/Shorts；支持多语言、批量渲染，也有 API 供 agent 调用。
- 什么时候用 / 常见坑：适合无真人出镜账号、日更测选题的场景；个人用免费，想拿它给客户做商用服务需要另购商业授权；自部署要自备模型服务，成本自己控制。

**适用场景**：想低成本批量起竖屏账号的个人、代运营团队、带 agent 的内容流水线。

**怎么用它搞钱**：带货短视频代运营。

**来源**：[IgorShadurin/app.yumcut.com](https://github.com/IgorShadurin/app.yumcut.com) · ⭐887 · 更新于 2026-09-03

### cutcli-cookbook

**核心提炼**
- 解决什么问题：手调剪映草稿慢、AI 写剪辑逻辑没法落地——用命令行/JSON 直接生成剪映草稿，桌面版打开就能继续手改。
- 核心用法（4 步）：1) `curl -s https://cutcli.com/cli | bash` 安装 → 2) 套 examples/ 或 templates/ 的 JSON 模板 → 3) `cutcli draft create` 等命令生成草稿 → 4) 打开剪映桌面版，草稿已在列表里，微调后导出；也可以把 prompts/ 丢给 Cursor/Claude Code，让 agent 驱动剪辑。
- 什么时候用 / 常见坑：剪映系模板化剪辑、口播批量生产时用；依赖剪映桌面版；云渲染要配 API key。

**适用场景**：会用 Cursor/Claude Code、想把剪辑变成代码流程的剪辑师和 agent 开发者。

**怎么用它搞钱**：剪辑外包 / 模板卖课。

**来源**：[xuliang2024/cutcli-cookbook](https://github.com/xuliang2024/cutcli-cookbook) · ⭐198 · 更新于 2026-05-26

### FireRed-OpenStoryline

**核心提炼**
- 解决什么问题：手动剪辑太慢、AI 一键成片又没法细改——用自然语言指挥剪辑（"把这段删掉""换个卡点音乐"），每一步可见、可改。
- 核心用法（4 步）：1) 装好（Python ≥3.11，有 OpenClaw/Claude Code 的 skill）→ 2) 上传素材、说清意图 → 3) agent 自动搜素材、写脚本、配音配乐加字幕 → 4) 对话式逐轮改（剪、换、重排），满意后导出；调好的工作流可存成 Skill，换素材批量复用。
- 什么时候用 / 常见坑：适合多条同类视频批量产（种草、测评、旅行 vlog）；AI 转场依赖第三方 AIGC 服务，成本高且效果不稳定，按需再开。

**适用场景**：想对话式剪辑、批量产出统一风格视频的个人创作者和小型团队。

**怎么用它搞钱**：接短视频代运营/批量带货视频单——一次建好 Skill，多客户复用。

**来源**：[FireRedTeam/FireRed-OpenStoryline](https://github.com/FireRedTeam/FireRed-OpenStoryline) · ⭐3479 · 更新于 2026-07-31

### X-Cut

**核心提炼**
- 解决什么问题：素材一堆但剪辑门槛高——聊天框里描述想法，agent 自动分析素材、写脚本、配音配乐、做 MG 动画，实时渲染到时间线上。
- 核心用法（4 步）：1) 部署（后端 FastAPI + 前端 React）→ 2) 上传素材，聊天说想法（如"做成旅行 vlog 加字幕"）→ 3) agent 选技能组合剪辑，Remotion 实时渲染预览 → 4) 不满意继续对话改，也可直接拖时间线微调；编辑配方可存为 Skill 复用或分享。
- 什么时候用 / 常见坑：旅行 vlog、产品宣传片这类"素材现成、缺剪辑"的场景；需要自己部署前后端，技术门槛比一键成片工具高。

**适用场景**：有技术基础、想搭自己剪辑 agent 的个人和团队。

**怎么用它搞钱**：给客户做"素材→成片"代剪辑服务，或把调好的 Skill 卖给同行。

**来源**：[MeiGen-AI/X-Cut](https://github.com/MeiGen-AI/X-Cut) · ⭐34 · 更新于 2026-04-22

### Rushes

**核心提炼**
- 解决什么问题：口播/长素材精剪费时——本地优先的对话式剪辑 agent，把自然语言意图转成可回退的原子时间线操作（删重复、去气口、按鼓点重排）。
- 核心用法（4 步）：1) 本地部署 → 2) 导入素材，系统建镜头/ASR/拍点索引 → 3) 对话下指令（"删掉重复这句""去掉太长的气口"）→ 4) agent 提交原子编辑（可审计、可回退），人工确认后导出；素材全在本地，模型只看最小必要信息。
- 什么时候用 / 常见坑：隐私敏感素材、长口播精剪场景；技术型项目，文档偏架构说明，上手要先读 docs。

**适用场景**：注重素材隐私、有开发能力的剪辑师/独立开发者。

**怎么用它搞钱**：做付费精剪服务（口播博主、课程创作者的长素材精修），按项目收代剪辑费。

**来源**：[nanzhi84/Rushes](https://github.com/nanzhi84/Rushes) · ⭐24 · 更新于 2026-08-09

## 收录标准

- 来源：X 博主实战分享（原帖 / 评论区 / 引用链）及 GitHub 高星项目
- 每条格式：核心提炼（解决什么问题 / 核心用法 / 什么时候用）+ 适用场景 + 「怎么用它搞钱」+ 来源链接
- Star 数为 2026-10-12 经 GitHub API 核验；持续收录中
- 去重：同一项目只收录一次，不堆 raw 链接

## 相关分类

- 总索引：[x-viral-video-skills](https://github.com/kkone1238899/x-viral-video-skills) —— 13 个分类导航
- [x-viral-video-scripts](https://github.com/kkone1238899/x-viral-video-scripts) —— 编剧 / 脚本
- [x-viral-video-hooks](https://github.com/kkone1238899/x-viral-video-hooks) —— 标题 / 5 秒钩子
- [x-viral-video-creative-direction](https://github.com/kkone1238899/x-viral-video-creative-direction) —— 创意总监
- [x-viral-video-directing](https://github.com/kkone1238899/x-viral-video-directing) —— 导演
- [x-viral-video-replication](https://github.com/kkone1238899/x-viral-video-replication) —— 复制爆款
- [x-viral-video-breakdown](https://github.com/kkone1238899/x-viral-video-breakdown) —— 拉片
- [x-viral-video-pipeline](https://github.com/kkone1238899/x-viral-video-pipeline) —— 流水线 / 生产管线
- [x-viral-video-de-ai](https://github.com/kkone1238899/x-viral-video-de-ai) —— 去 AI 味
- [x-viral-video-characters](https://github.com/kkone1238899/x-viral-video-characters) —— 人物构建
- [x-viral-video-prompt-opt](https://github.com/kkone1238899/x-viral-video-prompt-opt) —— 提示词优化
- [x-viral-video-copywriting](https://github.com/kkone1238899/x-viral-video-copywriting) —— 文案
- [x-viral-video-showcase](https://github.com/kkone1238899/x-viral-video-showcase) —— X 病毒视频合集

## 投稿

发现好的视听剪辑技巧 prompt / skill，欢迎提 Issue 或 PR（格式见 CONTRIBUTING.md）。

## 更新日志

- 2026-10-12：条目升级为小节式（核心提炼/适用场景/怎么用它搞钱），新增 3 个项目，Star 全部重新核验
- 2026-10-11：首版，2 个项目，持续收录中
