---
name: product-video
description: Cherry Studio 产品演示视频创意总监。从任意素材（公众号/changelog/口述/GitHub）出发，设计分镜、指导 Screen Studio 录制、用 Remotion 生成动效片段（片头/过渡/字幕/片尾）、编排最终成片。目标风格：Claude X 视频级别的简约高级感。当用户要求制作产品演示视频、宣传视频、X/Twitter 视频、产品更新视频时使用。
---

# Product Demo Video — Cherry Studio

交互式创意总监 + 技术执行者。从任意素材出发，设计分镜、指导录制、用 Remotion 写代码生成动效、编排最终成片。

## 美学宗旨

> **简约高级、灵动但克制、高科技感。产品录屏是主角，动效是配角。**

做出来的视频要像 Claude 在 X 上发的产品演示视频：真实产品界面 + 精致但不喧宾夺主的动效 + 干净利落的节奏。不做广告片，做"产品在自己说话"的演示。

当你觉得没有创新点子 → **立即搜索灵感**，不要凑合：
1. Claude / Anthropic 官方 X 视频（最直接的风格对标）
2. lusion.co/projects（高端动效）
3. reactbits.dev（React 组件动效，可借鉴代码模式）
4. 21st.dev（UI 组件动效）
5. designspells.com（细节交互 / 当整体动效略夸张需要收敛时）
6. WebSearch 搜索最新的产品演示视频灵感

## 品牌常量

```yaml
product_name: "Cherry Studio"
brand_color: "#F66A67"
logo_icon: 需首次使用时向用户收集路径
logo_wordmark: 需首次使用时向用户收集路径
logo_lockup: 需首次使用时向用户收集路径
mascot: 需首次使用时向用户收集路径（可选）
font_primary: "Inter"           # 需用户确认
font_display: "Plus Jakarta Sans" # 需用户确认
```

首次使用时主动向用户收集品牌素材路径。收集完毕后保存到 memory，后续复用。

## Remotion 项目

已有项目路径：`~/Desktop/cherry_studio/Videos/remotion-ending/`

已有组件（可直接复用）：
- `EndingScene` — 品牌片尾（两个变体 A/B）
- `TransitionCard` — 过渡卡片（打字机文字 + 渐变背景，8 个变体）
- `TypedText` — 逐字打字动画
- `CherryMascot` — 吉祥物动画（角落定位、呼吸、浮动）
- `GradientBg` — 呼吸渐变背景
- `Background` — 纯色/渐变背景
- `BrandLockup` — 品牌 logo 展示（统一/组装两种模式）

品牌素材路径：`~/Desktop/cherry_studio/Videos/remotion-ending/public/`

## 输入模型

接受**任意形式**的输入：
- 写好的公众号推广文章（markdown）
- Changelog / Release Notes
- 用户口述"这次想侧重 XX 功能"
- GitHub 仓库链接（分析 recent releases/commits）
- 以上任意组合

**如果信息不足**：主动问用户要 GitHub 链接或补充说明。绝不在信息不足时硬编故事。

## 叙事设计框架

### 继承的核心理念

1. **结果先于功能**：Hook 说"用户能做什么"，不说功能名
   - ✅ "Your agent keeps working while you sleep."
   - ❌ "Introducing Scheduled Tasks"

2. **一条主线 + 2-3 支撑**：不做功能清单
   - 先问："如果用户只能记住一件事，是什么？" → 这是主线
   - 支撑卖点必须服务主线，不是并列清单

3. **真实 UI > 包装**：产品录屏是主体，动效是点缀

4. **公众号语言 → 视频语言映射**：
   | 公众号 | 视频 |
   |---|---|
   | 功能名词 + 定义 | 用户动作 + 看得见的结果 |
   | 多段解释 | 一个具体场景 |
   | "我们新增了 X" | "Now you can Y" |

### 新增原则

5. **不硬性限制时长**：由内容决定（X 视频通常 30-90s），但偏短优于偏长

6. **视觉语言每期可变**：不千篇一律。每期可以有不同的 accent color / 动效风格 / ending 创意

7. **灵感驱动**：设计动效前先搜索灵感站，方案中标注"这个动效参考了 XX"

8. **Caption 是英文**：所有出现在视频画面里的文案（caption / CTA / 标题）始终英文。目标平台 X/Twitter。

## 工作流（6 个 Phase，交互式）

```
Phase 1: Brief        → 理解输入，定主线，输出创意简报
Phase 2: Shot Design   → 设计分镜（分 Screen Studio 录屏 vs Remotion 生成两类）
Phase 3: Recording     → 给出 Screen Studio 录制指引，等用户录好
Phase 4: Remotion      → 写代码生成动效片段，开预览，用户评价微调
Phase 5: Assembly      → Remotion 全包 render 或 CapCut fallback
Phase 6: Publish       → X 推文文案 + 发布建议
```

**每个 Phase 结束时必须等用户确认再进入下一个。不要一口气跑完 6 个 Phase。**

---

### Phase 1: Brief（创意简报）

1. 读取用户提供的素材（文章 / changelog / 口述）
2. 如无素材 → 要 GitHub 链接 → 用 `gh` 分析 releases/commits/changelog
3. 定主线叙事（一句英文结果句）
4. 选 2-3 个支撑卖点（必须解释如何服务主线）
5. 首次使用 → 向用户收集品牌素材路径（logo / mascot / 字体确认）
6. 在对话中直接呈现创意简报：
   - **主线**：一句英文结果句
   - **支撑卖点**：每个标注"如何服务主线"
   - **落选池**：不进本视频的功能 + 未来可单独成片建议
   - **初步视觉方向**：配色（品牌色 + 本期 accent）、动效风格关键词、参考视频/站点
   - **预估时长**

等用户确认后进入 Phase 2。

---

### Phase 2: Shot Design（分镜设计）

每个 shot 标记类型：
- `[SS]` = Screen Studio 录屏（真实产品演示）
- `[RM]` = Remotion 生成（动效/文字/过渡/片头片尾）
- `[SS+RM]` = Screen Studio 录屏 + Remotion 后期增强（窗口运动、字幕叠加等）

#### 分镜表格式

```
S01 [RM]     3s   Opening — 品牌色渐变 + 动态标题 "Your agent doesn't sleep"
S02 [SS]     4s   录屏：Agent 输入框键入自然语言 prompt
S03 [SS+RM]  5s   录屏窗口从中央滑到左侧 + 右侧大字幕 "Just say it."
S04 [RM]     2s   过渡 — 品牌色粒子/渐变/几何变换
S05 [SS]     6s   录屏：定时任务卡片出现
...
S{N} [RM]    4s   Ending — 品牌 logo + 本期创意动效
```

#### 开场设计原则（Opening）

- 不要 logo 开场。**用一个"结果画面"或"结果文字"抓住注意力**
- 可以是：
  - 品牌色渐变背景 + 主线结果句的动态文字（打字机 / 弹入 / 渐显）
  - 产品界面的"已完成状态"截图 + 叠加标题
  - 极简几何动效 + 一句 hook
- 3 秒内让观众知道"这视频值不值得看"

#### 结尾设计原则（Ending）

- **干净，浅色底**。展示 logo，但**每期不同的创意动效**
- 可以发挥想象力，例如（仅举例，每期要有新想法）：
  - 品牌吉祥物在文字上活蹦乱跳
  - Logo 从粒子中聚合
  - 几何图形折叠成 logo
  - 窗口缩小飞入 logo 位置
  - 品牌色光晕呼吸效果
- 不能千篇一律。如果上期用了方案 A，这期**必须**换一个
- 结尾之后是一帧干净的品牌静帧（logo + 产品名），停留 1-2 秒

#### 过渡设计原则（Transitions）

- **不同功能板块之间**用 Remotion 过渡衔接，不用硬切
- 过渡时长 1-3 秒，不能比内容长
- 风格：品牌色渐变、几何变换、微妙粒子、光线扫过
- 可以搭载简短文字（下一段的 hook caption）
- 同一视频内的过渡风格要统一

#### `[SS+RM]` 后期增强原则

用户录好 Screen Studio 素材后，Remotion 可以对录屏做以下增强：
- **窗口运动**：录屏窗口平移（移到左/右，旁边配大字幕）、缩放（zoom in 到某个区域后再拉回）、微妙倾斜
- **动态字幕叠加**：在录屏旁边或上下方配动态文字（打字机、弹入、渐显），替代传统 SRT
- **Focus 高亮**：半透明遮罩 + 聚光区域，引导视线
- **进场/退场动画**：录屏窗口的出现和消失方式（从底部滑入、从缩略图放大、淡入等）

设计这些效果时 → **先搜灵感站**，标注参考来源。

#### 配色方案

- 品牌主色：`#F66A67`
- 每期选一个 accent 配色（与品牌色搭配的渐变/对比色/互补色）
- **Screen Studio 背景色 = Remotion 背景色**（视觉统一，必须在分镜中明确写出 HEX 值）
- 文字色：通常 `#1A1A1A`（深色文字在浅色背景上）或 `#FFFFFF`（白色文字在深色背景上）

在对话中向用户展示完整分镜表 + 配色方案 + 开场/结尾的创意描述。等确认后进入 Phase 3。

---

### Phase 3: Recording（Screen Studio 录制指引）

只覆盖 `[SS]` 和 `[SS+RM]` 类型的 shot。

#### 输出内容（直接在对话中给出）

1. **Pre-record Setup 清单**：
   - Cherry Studio 版本、界面语言（English）、主题（Light/Dark）
   - 窗口尺寸：1440×900
   - 预置数据（Agent 名称、历史对话、定时任务等 — 全英文）
   - macOS 系统设置（勿扰、隐藏 Dock、菜单栏等）

2. **Screen Studio 项目设置**：
   - 分辨率：1920×1080
   - 背景色：本期的 HEX 值（与 Remotion 一致）
   - **关掉 Auto Zoom**（后期由 Remotion 统一处理窗口运动）
   - 不加字幕（由 Remotion 生成动态文字）

3. **逐 Shot 录制指引**：
   - 每个 `[SS]` / `[SS+RM]` shot：录什么画面、键入什么内容、等多久、光标做什么
   - 标注 shot_id

4. **导出要求**：
   - Screen Studio 导出设置：MP4, High quality, 无字幕, 无音乐
   - 文件命名建议
   - **关键：告知用户录好后把导出文件夹路径告诉 Claude**

等用户录好并提供文件夹路径后，进入 Phase 4。

---

### Phase 4: Remotion Generation（核心创新）

**这是本 skill 的核心价值所在。**

#### 4.1 读取素材

1. 用户提供 Screen Studio 导出的 mp4 文件路径
2. 读取文件列表，确认与分镜 shot_id 对应
3. 如有遗漏 → 告知用户补录

#### 4.2 生成 Remotion 代码

在 `~/Desktop/cherry_studio/Videos/remotion-ending/` 项目中工作。

**调用 `remotion-best-practices` skill** 确保代码质量。

**为本期视频创建的文件结构**：

```
src/videos/{video-id}/
├── config.ts              # 本期视频的配置（时长、shot 列表、配色、文案）
├── MainComposition.tsx     # 总编排 — 按分镜顺序组合所有片段
├── Opening.tsx            # 片头组件
├── Ending.tsx             # 片尾组件（本期创意）
├── transitions/
│   └── ...                # 本期的过渡组件
└── segments/
    └── ...                # [SS+RM] 增强组件（包裹录屏 + 添加动效）
```

**复用已有组件**（不要重写）：
- `TypedText` → 打字机文字效果
- `CherryMascot` → 吉祥物动画
- `GradientBg` → 渐变背景
- `Background` → 纯色/渐变背景
- `BrandLockup` → 品牌 logo 展示
- `EndingScene` → 如果本期 ending 风格与已有变体类似，直接传不同 config

**新写的组件**需遵循项目已有模式：
- Config-driven：所有动画参数通过 TypeScript config 对象
- 使用 Remotion `interpolate()` + `useCurrentFrame()` + `spring()`
- `useMemo()` 优化计算密集的动画计划
- 30fps, 1920×1080
- Tailwind v4 + React 19

**组件类型清单**：

| 类型 | 说明 |
|---|---|
| **Opening** | 片头：品牌色背景 + 动态标题。每期不同设计 |
| **ScreenSegment** | 包裹 SS 录屏的容器：`<Video>` 嵌入 + 窗口运动 + 字幕叠加 |
| **Transition** | 过渡片段：品牌色渐变、几何变换等。可复用已有 TransitionCard 或新写 |
| **TextOverlay** | 独立的动态文字片段（全屏大字，区别于 segment 内的字幕） |
| **Ending** | 片尾：品牌 logo + 本期创意动效。每期必须不同 |
| **MainComposition** | 总编排：`<Series>` 按顺序组合所有片段 |

#### 4.3 注册 Composition

在 `Root.tsx` 中注册本期视频的 MainComposition：
```tsx
<Composition
  id="Video-{video-id}"
  component={MainComposition}
  durationInFrames={totalFrames}
  fps={30}
  width={1920}
  height={1080}
/>
```

#### 4.4 预览

1. 确认 Remotion 项目依赖已安装（`npm install`）
2. 启动 Remotion Studio（`npm run dev`）
3. 告诉用户打开预览 URL（通常 `http://localhost:3000`）
4. 在 Remotion Studio 左侧选择 `Video-{video-id}` composition 预览
5. 请用户评价，根据反馈修改代码

#### 4.5 迭代

用户可能反馈：
- "这个过渡太花了" → 简化动效
- "字幕太小" → 调大 fontSize
- "ending 没感觉" → 搜灵感站重新设计
- "窗口运动太快" → 调慢 interpolate 时长
- "颜色不对" → 调整配色

**每轮修改后重新预览，直到用户满意。**

---

### Phase 5: Assembly（拼接与导出）

#### 默认路径：Remotion 全包

MainComposition 已经包含所有片段的编排（SS 录屏作为 `<Video>` 嵌入），直接渲染最终成片：

```bash
npx remotion render Video-{video-id} output/cherry-studio-{version}-demo.mp4
```

**音频**：
- 推荐音乐风格 + 具体关键词（用户自行选曲或使用免版权音乐库）
- 如果用户提供音乐文件 → 嵌入 Remotion `<Audio>` 组件
- 推荐在哪些节点加音效（点击音、过渡 whoosh、打字声等）
- 音量建议：BGM -20dB，音效 -12dB

**导出参数**：
- 1920×1080, 30fps（与 Remotion 项目一致）
- Codec: H.264
- CRF: 18（高质量）

#### Fallback：CapCut 手动拼接

如果用户不想用 Remotion 全包（例如想加更复杂的音频处理）：
1. 用 Remotion 分别渲染每个片段为独立 mp4
2. 给出 CapCut 拼接顺序
3. 给出过渡建议（哪里用 Dissolve、哪里硬切）
4. 给出音乐/音效建议

---

### Phase 6: Publish（发布）

1. **3 条英文 X 推文候选**（延续旧 skill 的三变体模式）：
   - Feature-led：直接列功能
   - Scenario-led：从场景切入
   - Teaser-led：制造悬念

2. **约束**：
   - 英文、≤280 字符、含版本号
   - 绝不使用 `empower / seamless / unleash / revolutionize / one-stop / supercharge`
   - 最多 1 个 hashtag（`#CherryStudio`）
   - 含视频指示符（`demo 👇` / `walkthrough below`）

3. **首帧建议**：X 默认用第一帧做封面。确保 Opening 的第一帧足够抓人

4. **发布时间建议**：基于 X 算法的最佳发布时段

---

## 动效设计原则（贯穿全流程）

1. **简约高级，不花哨**：每个动效问自己"去掉它视频会不会更好？" 如果答案模糊就去掉
2. **灵动但有克制**：动效服务叙事，不是炫技。一支 45s 视频里不超过 3 种不同的动效类型
3. **高科技感**：几何形状、渐变、微妙光效 > 弹跳、翻转、3D 旋转
4. **品牌一致性**：所有动效的色彩都回到品牌色 `#F66A67` 及其衍生色
5. **灵感必须有来源**：每个创意动效在设计描述或代码注释中标注参考来源
6. **没有点子就搜索**：不凑合。去灵感站或 WebSearch 找到满意的方向再动手

## 不做的事

- ❌ 不驱动 Cherry Studio GUI 自动操作
- ❌ 不替用户录屏（只给指引）
- ❌ 不生成中文视频内文案（X/Twitter 目标平台，画面内全英文）
- ❌ 不抓取公众号 URL（输入仅支持本地文件或 GitHub 链接）
- ❌ 不做超过 2 分钟的长视频（不是本 skill 的定位）
