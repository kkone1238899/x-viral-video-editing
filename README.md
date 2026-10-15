# 视听剪辑技巧

> 剪辑太慢赶不上热点？这个库收集 AI 剪辑和自动套剪的方法，每条都写清楚能帮你解决什么、怎么用它搞钱。
>
> A curated collection of editing techniques prompts & skills for viral short videos, gathered from practitioners sharing on X.
> 
> Each entry answers: what problem it solves (and who it's for), how to use it step by step, and how to make money with it.
> 
> Star counts verified via GitHub API on 2026-10-15. Continuously updated.

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

### claude-remotion-skill

**核心提炼**
- 解决什么问题：让 AI"做个视频"总产出平淡的淡入淡出、线性运动——把动态设计手艺编码成 Claude agent skill，用 Remotion 做专业级 MG 视频（弹簧动效、错峰编舞、调色、胶片颗粒、Ken Burns、逐词同步字幕、声音设计）。
- 核心用法（5 步）：1) 把仓库装成 Claude Code/Claude Desktop 的 skill → 2) 一句话描述想要的视频 → 3) Claude 按 skill 硬规则生成 Remotion 代码 → 4) 强制走"渲染→抽帧检查→修→再渲染"循环，自己验帧不裸奔 → 5) 导出成品。
- 什么时候用 / 常见坑：知识类、讲解类竖屏 MG 最对味；丢几帧参考帧给它，修帧循环才准；效果上限取决于例子质量。

**适用场景**：知识科普博主、课程创作者、想用 agent 批量产 MG 的团队。

**怎么用它搞钱**：知识付费账号的视觉代工（同风格批量套剪），或把调好的 skill 卖给同行。

**来源**：[haidrrrry/claude-remotion-skill](https://github.com/haidrrrry/claude-remotion-skill) · ⭐434 · 更新于 2026-10-14

### akari-video

**核心提炼**
- 解决什么问题："意图是人类的，手是 AI 的"——把素材丢给 agent，它做分析、剪辑、字幕、配音配乐，你只看成品、修偏离意图的地方。
- 核心用法（4 步）：1) 装桌面端（Theia 壳）或走无头路径（opencode / Claude Code / Cursor + 27 个 agent skills）→ 2) 丢素材进去 → 3) agent 完成分析剪辑到成品 → 4) 审片，只修不对的地方。
- 什么时候用 / 常见坑：不想学剪辑软件、只想当"审片人"时用；项目标注 under construction，迭代快，先跑无头 skill 路径更稳。

**适用场景**：不想学剪辑软件、只想当"审片人"的博主和团队。

**怎么用它搞钱**：短视频代运营的"剪辑外包"——接素材量大的客户，用 agent 批量消化。

**来源**：[AkariLabs/akari-video](https://github.com/AkariLabs/akari-video) · ⭐209 · 更新于 2026-10-14

### ai-video-editing-skill（Vlog Auto Edit）

**核心提炼**
- 解决什么问题：旅行拍了 80 个片段，回来永远懒得剪——中文 skill 教 AI Agent 用 ffmpeg + Whisper + Vision 自动理解素材、选片、排叙事，附 24 条实战踩坑经验。
- 核心用法（5 步）：1) 把仓库装给 Claude Code / Hermes / OpenClaw 等 agent → 2) 丢素材文件夹进去 → 3) agent 按 skill 的完整工作流（理解素材→选片→配音配乐→出片）自动执行 → 4) 可视化预览工具检查 → 5) 导出。
- 什么时候用 / 常见坑：vlog / 旅行 / 日常记录类素材最合适；中文文档上手快；24 条踩坑经验先读一遍再跑。

**适用场景**：囤了大量旅行/生活素材的中文博主。

**怎么用它搞钱**：旅行博主 / 本地探店账号的剪辑代工，按条收费。

**来源**：[znyupup/ai-video-editing-skill](https://github.com/znyupup/ai-video-editing-skill) · ⭐154 · 更新于 2026-10-12

### AIEV

**核心提炼**
- 解决什么问题：Claude 当导演——自动转录、写剪辑脚本、生成 kinetic typography 场景、卡拉 OK 字幕、鼓点同步变焦、时间戳音效，用 HyperFrames + Remotion 组装成 MP4，全程网页仪表盘监督。
- 核心用法（5 步）：1) 本地部署 → 2) 丢素材、简单描述想要的效果 → 3) 点"Start editing with AI" → 4) 仪表盘监督每一步（先出草稿再出终版，每帧可验）→ 5) 导出 MP4；支持多套品牌 kit（配色/字体/logo/语气），可一键下载 Google Fonts。
- 什么时候用 / 常见坑：品牌感强、字幕排版要求高的讲解/营销视频最合适；需要自部署，有一点技术门槛。

**适用场景**：做品牌内容、知识类视频的个人和团队。

**怎么用它搞钱**：品牌宣传片 / 课程片的剪辑外包——品牌 kit 一次调好，多客户复用。

**来源**：[notivn/AIEV](https://github.com/notivn/AIEV) · ⭐135 · 更新于 2026-10-14

### oh-my-cassette

**核心提炼**
- 解决什么问题：中文"随身 AI 剪辑搭档"——AI 剪辑插件 + MCP 服务器，给 Claude Code / Codex / Hermes / OpenCode 用的聊天式剪辑。
- 核心用法（4 步）：1) 按仓库说明装插件 / MCP → 2) 在 agent 里聊天描述剪辑意图 → 3) agent 调用剪辑能力处理素材 → 4) 导出成片。
- 什么时候用 / 常见坑：中文项目文档友好；装之前看 releases 选稳定版；montage 拼贴类剪辑场景。

**适用场景**：习惯在 Cursor / Claude Code 里干活的中文创作者。

**怎么用它搞钱**：接"素材→成片"代剪辑单，或给团队搭剪辑 MCP 收服务费。

**来源**：[Cassette-Editor/oh-my-cassette](https://github.com/Cassette-Editor/oh-my-cassette) · ⭐120 · 更新于 2026-10-12

### OpenCut（Premiere Pro 版）

**核心提炼**
- 解决什么问题：Premiere Pro 本地 AI 剪辑自动化——去静音/去废话、自动字幕、音频修复、社媒导出，全在本机跑，核心功能无订阅、无需 API key。
- 核心用法（4 步）：1) Python 3.11–3.14 装好 → 2) 装 OpenCut（Premiere Pro 2019+）→ 3) 跑去静音 / 字幕 / 音频修复等自动化 → 4) 一键导出社媒规格。
- 什么时候用 / 常见坑：PR 重度用户、口播/播客类长素材的"粗剪"阶段最划算；Windows / macOS / Linux 都支持；MCP 也能调。

**适用场景**：用 PR 的剪辑师、播客 / 口播博主。

**怎么用它搞钱**：口播博主的"粗剪外包"——接长素材，自动化粗剪 + 人工精修两段收费。

**来源**：[SysAdminDoc/OpenCut](https://github.com/SysAdminDoc/OpenCut) · ⭐62 · 更新于 2026-10-14

### cutcraft

**核心提炼**
- 解决什么问题：Codex 用的完整 AI 剪辑生产系统——"一句话进，一部成片出"：看素材、定创意方向、剪辑、精修声音画面、验导出，全流程可控可续跑，不止于转录和上字幕。
- 核心用法（4 步）：1) 装给 Codex → 2) 一句话描述需求 → 3) 它理解素材→锁定创意方向→剪辑→精修声音画面 → 4) 验导出，并留一份可继续改的过程文件。
- 什么时候用 / 常见坑：想"交钥匙"式成片、不想在时间线和导出文件夹之间来回折腾时用；附中文一句话介绍。

**适用场景**：想全权交给 agent 的独立创作者。

**怎么用它搞钱**：短视频代运营——同一工作流批量套不同客户素材。

**来源**：[chang416/cutcraft](https://github.com/chang416/cutcraft) · ⭐52 · 更新于 2026-09-17

### open-edits

**核心提炼**
- 解决什么问题：Claude Code 用的口播头剪辑 harness——raw talking-head 进来，出去是全动画短片：动态图形、kinetic 字幕、真人脸/真 logo、reaction GIF、b-roll 卡片、滚动计数器，全按你说的每个词卡点；Python 本地绘制渲染，无付费生成。
- 核心用法（4 步）：1) 把 skills 装给 Claude Code → 2) 丢口播原片 → 3) 选 skill（竖屏分屏 / 横屏长视频 / 脚本生成 / AI 数字人版）→ 4) Claude 本地渲染出片。
- 什么时候用 / 常见坑：作者在自己 YouTube 频道每天实战用，真刀真枪验证过；口播 / 知识类竖屏最对味。

**适用场景**：口播博主、知识类竖屏账号。

**怎么用它搞钱**：口播账号的"剪辑升级"服务——同一个人设，多风格动画套剪。

**来源**：[kevinbadi/open-edits](https://github.com/kevinbadi/open-edits) · ⭐41 · 更新于 2026-10-14

### favstash-ai-video-editing-skills

**核心提炼**
- 解决什么问题：九个 skill 打通短视频全链路——找选题→写脚本→剪辑（5 种成品风格）→发布→看数据复盘，教 Claude Code / Codex 全自动跑。
- 核心用法（4 步）：1) 按 INSTALL_FOR_AGENTS.md 把九个 skill 装进 workspace → 2) 连上 FavStash（CLI 或引导登录）→ 3) agent 跑完整循环：找爆款选题→写你的口吻脚本→剪辑→定时发布→分析数据 → 4) 按数据调下一轮。
- 什么时候用 / 常见坑：想"选题-生产-发布-复盘"一条龙自动化时用；依赖 FavStash 平台账号做发布和分析。

**适用场景**：想跑矩阵号、日更测选题的团队和个人。

**怎么用它搞钱**：短视频矩阵代运营——一套 agent 流程管多个账号。

**来源**：[alisadiq-ai/favstash-ai-video-editing-skills](https://github.com/alisadiq-ai/favstash-ai-video-editing-skills) · ⭐24 · 更新于 2026-10-14

### @zhu185178：Opus 5.5 当导演跑通 AI 短剧（挑片与可追溯流程）

**核心提炼**（聚焦挑片/审片环节）
- 让模型先反问再干活：把 1500 字剧本交给模型，它先建项目文件、再追问用途/平台/画风/预算/质量 5 个问题——"先反问后出活"这套逻辑自搭 harness 也能照搬。
- 画风三选一并排看：同一场戏先出 3 张不同画风样图（真人古装、3D 国漫、2D 国风）并排选，避开对"电影感"这类词的理解偏差。
- 角色一致性配方：每个角色一张图里放三视图（胸像特写+全身正面+全身侧面）再加一个辨识特征，解决换镜头换脸。
- 片名字不出错：只靠提示词描述会出假字，首尾帧图片约束让片名四个字一笔不错。
- 挑片两阶段：每段生成 3 条候选，先过硬指标（脸像不像、台词对不对、音量合不合），再谈审美。
- 全程可追溯：每段能看到候选条数、选中哪条、提示词、参考图、首尾帧，方便复盘重做。
- 算总账：全片约 106 美元（文生图和配乐订阅未计入）；单价便宜不等于总价便宜，看整片总账。

**适用场景**：用 AI 生成+人工挑片做短剧/系列短片的个人和团队。

**怎么用它搞钱**：短剧代工的"AI 制片"服务——一次跑通流程，多剧复用。

**来源**：[@zhu185178 原帖](https://x.com/zhu185178/status/2110385140837056621)（2026-10-14 23:00）

### @yang_xin19：口播+AI 剪辑涨粉账

**核心提炼**
- 拆开看全流程：选题剧本→拍摄出镜→剪辑（Agent 擅长的脏活：去废词、压停顿、微调语速、推镜、字幕节奏）→包装（B-roll、数据卡片、音效），包装 AI 只能给草案，记忆点得自己定。
- 正确归因："6 分钟剪完"只是剪辑耗时，不是做号总成本——案例博主已稳定更新 3 个月、主页有 5 条爆款打底。
- 不绑一家的口播流水线：粗剪交给规则（去废词、压停顿、自动上字幕），精修留给判断（梗图、何时抛观点留人工）；具体工具只是第三步的可选引擎。
- 发完复盘三个数：点击差→改封面标题；完播差→改节奏和前 15 秒；收藏高→下条把方法写更清楚。
- 算账口径：AI 剪辑工具月费 vs 外包约 80 元/条（月发 30 条约 2400 元）vs 兼职约 6000 元/月——结论是"AI 出粗剪+人过一轮"。
- 决策逻辑：瓶颈是素材堆着剪不动→上 AI 剪辑；瓶颈是出镜和选题→先练镜头。出镜和选题定流量上限，工具把时间成本打下来。

**适用场景**：口播账号、想量化剪辑投入产出比的博主。

**怎么用它搞钱**：用"AI 粗剪+人工精修"接口播代剪辑，按月收服务费。

**来源**：[@yang_xin19 原帖](https://x.com/yang_xin19/status/2110425728726749615)（2026-10-15 01:41）

### @vrainerd：图生视频多段拼接工作流

**核心提炼**
- 核心思路：纯文生视频难控制，先精心生成一张满意的首帧（构图、光线、人物在这一步定好），视频的画面、风格、角色就定下来了。
- 写运动提示词：不再描述画面里有什么，只描述"怎么动"（镜头缓慢前推、人物转头微笑、树叶轻摇）。
- 控制运动幅度：越复杂越易穿帮变形，新手从简单运动开始（推拉、轻微表情、自然环境动态）。
- 多版本抽卡：视频"抽卡率"比图片高，同一提示词多生成几次再挑。
- 剪辑拼接：单段多为 10-20 秒，长视频靠多段剪辑拼接，保持每段首帧角色和风格一致。
- 工具组合参考：Nano Banana 2 Lite 生图 + Gemini Omni Flash 转视频；字节 Seedream/Seedance、快手可灵都以图生视频为核心能力。

**适用场景**：用 AI 做系列短片、短剧，需要多段拼接的创作者。

**怎么用它搞钱**：AI 短剧的"拼接剪辑"代工——客户出图，你负责运动+拼接成片。

**来源**：[@vrainerd 原帖](https://x.com/vrainerd/status/2110526743861977519)（2026-10-15 08:22）

### @grokkedd：15 个 repos 把 Opus 5.5 变成动态设计工作室

**核心提炼**
- 方法论：按"任务"分类装 skills——发布视频 / 剪辑自有素材 / 短动画 / 网站动画 / 官方项目，建议先切换到 Opus 5.5。
- 剪辑自有素材类：hyperframes-student-kit（nateherkai）——给原始素材，自动剪掉停顿和失误、收紧叙事、加动画图形；motion-graphics（Barty-Bart）——在你说话的时刻加动画，还能把人从背景抠出来。
- 发布视频类：product-launch-motion（AbubakrChan）——给产品，自动写脚本、加配音、设运镜调色，返回成片；motion-graphics-skills（charlie947）——13 个技能做发布视频、动画图表、短片段；claude-motion-design（howseen-ai）——画面声音卡音乐节拍。
- 短动画类：animate（cth9191）——7 种风格短解说（剪纸、孔版印刷、像素风等），开工前先出分镜；claude-motion（whaleyxbt）——给 AI 艺术指导品味、让它自查画面、自己构建音效。
- 官方项目兜底：heygen-com/hyperframes、remotion-dev/remotion 官方 skills、greensock/gsap-skills、LottieFiles/motion-design-skill（迪士尼动画原则改编给 AI）。
- claude-remotion-skill（haidrrrry）——修复 AI 生成视频僵硬运动；已收录本库，不再重复。

**适用场景**：想用 Claude 做动态设计/产品发布视频的创作者。

**怎么用它搞钱**：产品发布视频代工——产品进、成片出。

**来源**：[@grokkedd 原帖](https://x.com/grokkedd/status/2110431011477529030)（2026-10-15 02:02）

### @byCanen：ffmpeg-skill——给 coding agent 的本地剪辑师

**核心提炼**
- 定位：Agent Skill，把 FFmpeg 剪辑能力交给 Claude Code / Codex / Cursor 调用；不需要云端视频生成 API，视频在本机处理。
- 几十种操作：剪切、拼接、静音检测、字幕、横竖屏转换、响度处理、HDR 转 SDR 等。
- 安装：Claude Code 用 npx ffmpeg-skill；Codex 加 --codex；Cursor 加 --cursor；配好先跑 npx ffmpeg-skill doctor 检查本机编码器和滤镜。
- 任务 prompt 模板：先检查分辨率/帧率/编码/音轨→剪掉开头 3 秒→转 9:16→加 SRT 字幕→统一响度→导出 Shorts MP4；能无损处理的步骤优先无损。
- 它会对结果重新 probe，涉及画面修改时可输出接触表辅助检查。

**适用场景**：习惯命令行/agent 干活、想把剪辑变成可复用任务的创作者和开发者。

**怎么用它搞钱**：批量竖屏化代工——长视频批量转 Shorts，按条收费。

**来源**：[@byCanen 转述帖](https://x.com/byCanen/status/2110373181882011964)（2026-10-14 22:12，引用链 @KowalPrato4o 实测整理） · GitHub 项目 [kajisho5/ffmpeg-skill](https://github.com/kajisho5/ffmpeg-skill) · ⭐1944 · 更新于 2026-10-14

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
- 2026-10-15：早档新增 14 条（X 5 条：AI 短剧挑片流程 / 口播 AI 剪辑涨粉账 / 图生视频多段拼接 / Opus 动态设计 15 repos / ffmpeg-skill；GitHub 9 个项目：claude-remotion-skill / akari-video / ai-video-editing-skill / AIEV / oh-my-cassette / OpenCut / cutcraft / open-edits / favstash-ai-video-editing-skills），Star 全部经 GitHub API 核验
- 2026-10-11：首版，2 个项目，持续收录中
