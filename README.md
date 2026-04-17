# product-video

Cherry Studio 产品演示视频的端到端制作 skill。从"有个更新想发 X"到"成片 + 推文"，6 个 Phase 交互式完成。

## 一句话定位

> 你的 AI 创意总监：设计分镜、指导你录屏、用 Remotion 写代码生成动效、编排成片、写推文。

## 它解决什么问题

以前做一支产品视频：写脚本 → 自己想分镜 → 录屏 → 找素材做片头片尾 → 手动剪辑拼接 → 调字幕 → 写推文。每个环节都要切工具、查参考、反复调整。

现在：你提供素材（文章 / changelog / 甚至一句话），skill 帮你走完全程。你只需要做两件事——**录 Screen Studio** 和 **看预览说"改这里"**。

## 快速开始

```
/product-video 这次 v1.9.1 主要更新了 Agent 自主模式，我想做一支 X 视频
```

或者：

```
/product-video 帮我看看这个 changelog，挑最适合拍视频的功能
```

再或者：

```
/product-video https://github.com/CherryHQ/cherry-studio
```

Skill 会从 Phase 1（创意简报）开始，每一步等你确认再推进。

## 工作流总览

```
Phase 1: Brief         你给素材 → 我定主线叙事 + 配色 + 风格方向
                        ↓ 你确认
Phase 2: Shot Design    我设计分镜表（标注哪些镜头你录、哪些我用代码生成）
                        ↓ 你确认
Phase 3: Recording      我给你 Screen Studio 录制指引 → 你去录
                        ↓ 你录好，把文件夹路径给我
Phase 4: Remotion       我写代码生成片头/过渡/字幕动效/片尾 → 开预览 → 你看效果
                        ↓ 你满意（或反复微调直到满意）
Phase 5: Assembly       我用 Remotion 渲染成片（或给 CapCut 拼接方案）
                        ↓ 成片导出
Phase 6: Publish        我写 3 条英文推文候选 → 你选一条发 X
```

## 前置依赖

| 工具 | 用途 | 安装 |
|---|---|---|
| **Screen Studio** | 录制产品演示 | macOS 应用，需自行购买 |
| **Node.js ≥ 18** | 运行 Remotion | `brew install node` |
| **Remotion 项目** | 生成动效片段 | 已存在于 `~/Desktop/cherry_studio/Videos/remotion-ending/` |
| **CapCut**（可选） | Fallback 拼接方案 | 免费桌面版 |

首次使用前确认 Remotion 项目依赖已安装：
```bash
cd ~/Desktop/cherry_studio/Videos/remotion-ending && npm install
```

## 品牌素材

首次使用时 skill 会问你要以下素材路径：

| 素材 | 说明 | 现有位置 |
|---|---|---|
| Logo icon | 产品图标 | `remotion-ending/public/cherry-studio-icon.png` |
| Logo wordmark | 文字商标 | `remotion-ending/public/cherry-studio-wordmark.png` |
| Logo lockup | 完整 logo | `remotion-ending/public/cherry-studio-lockup.png` |
| Mascot | 吉祥物（可选） | `remotion-ending/public/cherry-mascot.png` |

品牌主色：`#F66A67`

## 输入类型

Skill 不挑输入格式，以下都行：

- **公众号推广文章**（markdown）— 最完整，skill 能提取功能分级 / 操作路径 / 场景
- **Changelog / Release Notes** — 精炼，skill 会补充场景设计
- **一句话口述** — "这次想突出 Agent 自主模式"，skill 会追问细节
- **GitHub 仓库链接** — skill 用 `gh` 分析最近的 release / commits
- **以上混搭** — 比如"看看这个 changelog，但我想侧重定时任务"

## 输出

不是 markdown 文档包。是**可渲染的代码 + 成片视频**：

```
~/Desktop/cherry_studio/Videos/remotion-ending/
└── src/videos/{video-id}/
    ├── config.ts              # 本期配置（时长、配色、文案）
    ├── MainComposition.tsx     # 总编排
    ├── Opening.tsx            # 片头
    ├── Ending.tsx             # 片尾（每期不同创意）
    ├── transitions/           # 过渡片段
    └── segments/              # 录屏增强（窗口运动 + 字幕叠加）

~/Desktop/cherry_studio/Videos/remotion-ending/output/
└── cherry-studio-{version}-demo.mp4   # 最终成片
```

## 美学标准

**对标**：Claude / Anthropic 的 X 产品视频

**关键词**：简约高级、灵动但克制、高科技感

**具体规则**：
- 产品录屏是主角，动效是配角
- 每个动效问"去掉它视频会不会更好？"，模糊就去掉
- 一支视频不超过 3 种动效类型
- 几何 / 渐变 / 微妙光效 > 弹跳 / 翻转 / 3D 旋转
- 片尾每期不同创意，不能千篇一律
- 没有点子不凑合 → 搜灵感站再动手

**灵感来源**（skill 会主动去这些站搜索）：
- Claude / Anthropic X 视频
- [lusion.co/projects](https://lusion.co/projects)
- [reactbits.dev](https://reactbits.dev/)
- [21st.dev](https://21st.dev/home)
- [designspells.com](https://www.designspells.com/)

## 与旧 skill 的关系

| | 旧 `release-to-video` | 新 `product-video` |
|---|---|---|
| 输入 | 仅 markdown 文章 | 任意形式 |
| 输出 | 7 个 markdown 文档 | Remotion 代码 + 成片视频 |
| 动效 | 不参与 | Remotion 生成 |
| 字幕 | SRT 文件 | Remotion 动态文字 |
| 交互性 | 批量生成 | 6 Phase 交互迭代 |
| 拼接 | 用户手动 CapCut | Remotion 一键 render |

旧 skill 保留不动，新 skill 完全独立。

## 共享 Remotion 组件

Skill 在生成代码时会复用项目中已有的组件：

| 组件 | 路径 | 用途 |
|---|---|---|
| `ScreenSegment` | `src/shared/ScreenSegment.tsx` | 包裹 SS 录屏 + 窗口运动 + 字幕叠加 |
| `EndingScene` | `src/ending/EndingScene.tsx` | 品牌片尾（可传不同 config） |
| `TransitionCard` | `src/transitions/TransitionCard.tsx` | 打字机过渡卡片 |
| `TypedText` | `src/transitions/TypedText.tsx` | 逐字打字动画 |
| `CherryMascot` | `src/transitions/CherryMascot.tsx` | 吉祥物角落动画 |
| `GradientBg` | `src/transitions/GradientBg.tsx` | 呼吸渐变背景 |
| `BrandLockup` | `src/ending/BrandLockup.tsx` | Logo 展示（统一 / 组装模式） |

每期视频的 Opening / Ending / 特殊 Transition 会**新写**，因为每期要有不同创意。

## FAQ

**Q: 我不会用 Screen Studio，也能用这个 skill 吗？**
A: Phase 3 会给你详细的录制指引（点哪里、键入什么、等多久）。但你需要自己操作 Screen Studio 完成录制。

**Q: 视频里的文字是中文还是英文？**
A: 画面内全英文（caption / 标题 / CTA）。目标平台是 X/Twitter。录制 Cherry Studio 时也切英文界面。

**Q: 我能只用 Remotion 不用 Screen Studio 吗？**
A: 不推荐。产品录屏是真实 UI，这是"产品自己说话"的核心。Remotion 只负责动效装饰，不替代录屏。

**Q: 如果我对预览效果不满意怎么办？**
A: Phase 4 是迭代式的。告诉我哪里不对，我改代码后重新预览，反复调到你满意。

**Q: 每次都要重新建 Remotion 组件吗？**
A: 共享组件（ScreenSegment / TypedText / BrandLockup 等）是复用的。每期只新写 Opening / Ending / 特殊 Transition — 因为每期要不一样。
