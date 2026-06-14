---
name: frontend-design
description: Use when building, designing, or redesigning any frontend interface — components, pages, apps, or prototypes. Covers design direction selection, typography pairing, color systems, motion/animation, spatial composition, responsive layout, accessibility, and anti-pattern avoidance.
---

# Frontend Design

指导生成辨识度高的生产级前端界面，避免通用 AI 审美。在写任何代码之前，必须先经过设计思考流程。

## 1. 设计思考（写代码前强制执行）

按顺序回答以下四个问题：

### 1a. Purpose（目的）
这个界面解决什么问题？谁用它？在什么场景下使用？

### 1b. Tone（调性）
选择一个明确的美学方向（或自行创造），并说明为什么它适合这个场景：

`brutalist` / `brutally minimal` / `maximalist chaos` / `retro-futuristic` / `organic-natural` / `luxury-refined` / `playful-toy` / `editorial-magazine` / `art-deco-geometric` / `soft-pastel` / `industrial-utilitarian` / `tech-corporate` / `editorial-magazine`

不只是从列表选——要根据场景设计一个真正属于这个界面的方向。

### 1c. Constraints（约束）
技术限制（框架、性能、浏览器兼容）、时间、内容来源。

### 1d. Differentiation（差异化——最关键的问题）
**这个界面让人记住的是什么？** 一个大胆的排版选择？一个出乎意料的动效？一个打破网格的布局？如果没有任何让人记住的点，重新思考设计方向。

> **关键原则**：大胆的极繁和克制的极简都可以——关键是 **有意为之**，不是强度问题。

## 2. 反模式清单（以下内容严格禁止）

**NEVER** 使用以下"AI 味"设计：

| 类目 | 禁止项 |
|------|--------|
| 字体 | Inter、Roboto、Arial、system-ui 等通用字体 |
| 配色 | 紫色渐变 + 白色背景（最普遍的 AI 模板） |
| 布局 | 可预测的三栏卡片布局、对称排列 |
| 组件 | 模板化卡片、默认导航、千篇一律的表单 |

**生成多样性约束**：连续多次生成时，不得每次都选相同或相似的风格（特别是 Space Grotesk 字体和深色渐变卡片这类 Common Choice）。每次的设计方向、色板、字体搭配必须有意识地差异化。

## 3. 实现复杂度匹配

设计方向的复杂度决定了代码的复杂度：

| 设计方向 | 代码要求 |
|----------|----------|
| 极繁/大胆 | 大量动画、丰富效果、复杂布局、装饰细节 |
| 极简/克制 | 精密的间距、精准的字体、微妙细节、大量留白 |
| 中间方向 | 匹配适当的复杂度，不堆砌也不简陋 |

**优雅来自对方向的精准执行，而不是堆叠功能。**

## 4. 前端审美指南

### 4a. 字体系统

- 选择 **有特色** 的字体，避免 Arial、Inter、Roboto
- **对字体搭配**：一个特色展示字体（display）+ 一个精致正文字体（body）
- 用 CSS 定义字体比例尺：`--text-xs` 到 `--text-4xl`
- Google Fonts 或 `@font-face` 自托管

### 4b. 色彩与主题

- 用 CSS 自定义属性（变量）定义完整色板，禁止硬编码十六进制值
- **主色 + 锐利强调色** 优于均匀分布的多色板
- 明/暗主题至少准备一套
- 所有颜色必须有语义化命名（`--color-primary` 而非 `--color-blue`）

### 4c. 动效与动画

- **CSS-only 优先**，HTML 场景优先用纯 CSS 实现动效
- React 场景优先用 Motion 库
- **交错出现**（staggered reveals）：用 `animation-delay` 实现页面加载时的渐进展示，这比零散微交互更令人印象深刻
- **滚动触发**：`IntersectionObserver` 或 CSS `animation-timeline`
- **悬停惊喜**：hover 状态的变换超出预期（色彩反转、缩放、变形、背景切换）
- 优先高冲击时刻：一个好的入场动画胜过十个微交互

### 4d. 空间构图

打破常规布局，让视觉有张力：

- **不对称**：不居中、不对称的栅格
- **重叠**：元素之间的前后叠放
- **对角线**：斜向切割或流向
- **破格**：元素突破容器边界
- **留白**：慷慨的负空间（极简方向）或受控的密度（信息密集方向）

### 4e. 背景与视觉细节

不要默认使用纯色背景。根据整体美学方向添加以下效果：

`gradient meshes`（渐变网格） / `noise textures`（噪点纹理） / `geometric patterns`（几何图案） / `layered transparencies`（透明叠加） / `dramatic shadows`（戏剧阴影） / `decorative borders`（装饰边框） / `custom cursors`（自定义光标） / `grain overlays`（颗粒覆盖）

选择 1–2 种与设计方向匹配的技法，不要全部使用。

### 4f. 组件状态覆盖

每个交互组件必须覆盖以下状态，用 CSS 或框架语法实现：

`rest` / `hover` / `focus-visible` / `active` / `disabled` / `loading` / `empty` / `error`

### 4g. 响应式

- **移动优先**，从小屏到大屏
- 用 CSS 变量定义断点：`--bp-sm: 640px`、`--bp-md: 768px`、`--bp-lg: 1024px`、`--bp-xl: 1280px`
- 每个组件至少验证两个断点
- 触屏设备考虑 `touch-action`

### 4h. 无障碍

- 所有 `<img>` 必须有 `alt` 文本
- 交互元素必须有 `:focus-visible` 样式
- 颜色对比度 ≥ 4.5:1（正规文本）/ ≥ 3:1（大文本）
- 表单控件必须关联 `<label>`
- 使用语义化 HTML（`<nav>`, `<main>`, `<section>`, `<button>` 而非 `<div>`）
- `aria-label` / `aria-describedby` 补充必要信息

## 5. 验证清单

代码输出前逐条确认：

- [ ] 是否完成了设计思考四步（Purpose→Tone→Constraints→Differentiation）？
- [ ] 是否选择了明确的美学方向并说明理由？
- [ ] 是否避免了所有反模式（通用字体/紫色渐变/模板布局）？
- [ ] 是否用 CSS 变量而非硬编码值？
- [ ] 是否有动效（至少一处交错出现或悬停惊喜）？
- [ ] 是否有响应式断点？
- [ ] 组件是否有 hover/focus/active/disabled 状态？
- [ ] 是否满足无障碍最低要求（alt/对比度/focus-visible）？
- [ ] 这次的设计与上次是否有意识地不同？
