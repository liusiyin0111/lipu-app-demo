# 梨谱 (LiPu) App 设计系统

> 从 Figma 设计文件提取的完整设计系统，供 AI 编码工具生成 UI 使用。
> Figma 文件: `Ozi96nfI4eKaYl87jJkzH2`

**设计基调**：暖色调 `#F8F5EF` 米白 + iOS 原生风格 (PingFang SC, 毛玻璃) + 品牌紫 `#7168D6` + 不对称圆角（气泡和卡片用"一角直角"暗示方向） + 暖色调阴影 `rgba(77,53,50,...)` + 对话驱动交互

---

## 1. 基础设备参数

| 参数 | 值 |
|------|-----|
| 设计尺寸 | 393 × 852 (iPhone 15 Pro) |
| 状态栏高度 | ~54px |
| Home Indicator | 26-34px |
| 安全区底部 | 36px |

---

## 2. 色彩系统

### 背景色

| Token | 值 | 用途 |
|-------|-----|------|
| bg-primary | `#F8F5EF` | 主背景，类米白 |
| bg-white | `#FFFFFF` | 卡片、输入框、底部面板 |
| bg-component | `#F9F9FC` | AI 气泡、Toast、Alert、Nav Bar |
| bg-bubble-user | `#EFEEFC` | 用户气泡 |
| bg-muted | `#E7E6ED` | 日记列表、Menu、取消按钮 |
| bg-task | `#F9F5EC` | 任务面板 |
| bg-hero | `#9CB9CA` | 3D 角色展示区（万物皆有灵底色） |
| bg-intro | `#F4ECE4` | Onboarding Intro 暖棕 |
| bg-input | `#F3F0E9` | 输入框底色、Avatar 框 |
| bg-viewfinder | `#19181B` | 万物皆有灵取景框 |

### 渐变

| Token | 值 |
|-------|-----|
| gradient-purple | `linear-gradient(180deg, #DBD8FF 0%, #EDEBFF 50%, #FFF 100%)` |
| gradient-onboarding | `linear-gradient(180deg, #E4E3ED 0%, #EFEEFC 50%, #FCFBF9 100%)` |
| gradient-topbar-fade | `linear-gradient(180deg, #F8F5EF 0%, rgba(248,245,239,0) 100%)` |
| gradient-topbar-chat | `linear-gradient(180deg, #D9D7F4 0%, transparent 100%)` |
| gradient-topbar-dark | `linear-gradient(180deg, rgba(40,39,55,0.5) 0%, rgba(40,39,55,0) 100%)` |
| gradient-action-bar | `linear-gradient(180deg, transparent 0%, #F4E8D7 100%)` |
| gradient-warm | `linear-gradient(180deg, #F0EBE2 0%, #F8F5EF 100%)` |
| gradient-intro-mask | `linear-gradient(180deg, #E2D4EA 0%, rgba(244,236,228,0) 100%)` |
| gradient-login-glow | `linear-gradient(270deg, #FFE5DB 9%, #EE8574 96%)` + blur(200px), opacity 50% |

### 品牌色

| Token | 值 | 用途 |
|-------|-----|------|
| brand-purple-deep | `#7168D6` | CTA 按钮、发送按钮 |
| brand-purple | `#987CFC` | 星仔 Avatar |
| brand-purple-light | `#C6B0FC` | 星仔紫浅 |
| brand-purple-disabled | `#D9D7F4` | 禁用态按钮 |
| brand-coral | `#F8837C` | 危险按钮、挂断按钮 |
| brand-pink | `#EE8574` / `#FFE5DB` | 登录页装饰 |
| brand-green | `#92E27C` | 任务头像绿 |
| brand-orange | `#F99F93` | 任务头像橙 |
| brand-gold | `#F8D8A8` | 任务头像金 |

### 文字色

| Token | 值 | 用途 |
|-------|-----|------|
| text-primary | `#000000` | 页面标题 |
| text-dark | `#1D1D1F` | Onboarding Intro 大标题 |
| text-warm | `#352E26` | 登录标题、问题正文 |
| text-gray | `#424245` | 副文描述 |
| text-bubble | `#282737` | 气泡内文字、Nav 标题、Toast |
| text-date | `rgba(40, 39, 55, 0.3)` | 日期标签 |
| text-hint | `rgba(53, 46, 38, 0.2)` | "内容由 AI 生成" |
| text-privacy | `rgba(53, 46, 38, 0.66)` | 隐私协议 |
| border | `rgba(0, 0, 0, 0.04)` | 分割线、边框 |
| overlay | `rgba(0, 0, 0, 0.2)` + blur | 弹窗遮罩 |

---

## 3. 字体系统

| Token | 字重 | 字号 | 行高 | 字间距 | 用途 |
|-------|------|------|------|--------|------|
| **Large Title** | 600 | 34px | 1.3em | -1.35% | Intro 大标题 |
| **Title 1** | 400 | 28px | 1.4em | -1.5% | 角色名展示 |
| **Title 3/Medium** | 500 | 20px | 1.4em | -1.5% | Alert 标题、副标题 |
| **Heading/H4** | 400 | 20px | 1.5em | -1% | 页面标题 |
| **Body 1/Medium** | 500 | 17px | 1.5em | -2.54% | Intro 正文 |
| **Body 2/CTA** | 500 | 16px | 1.35em | -1% | 按钮文字 |
| **Body 2/Regular** | 400 | 16px | 1.5em | -1% | 气泡正文、Nav 标题 |
| **Body 2/Medium** | 500 | 16px | 1.5em | -1% | 任务正文、Alert 按钮 |
| **Body 3/Regular** | 400 | 14px | 1.35em | -1% | Toast、小号按钮 |
| **Caption 1** | 400 | 12px | 1.3em | 0 | 隐私协议、日期、新消息 |
| **Body/Large** | 500 | 24px | 1.33em | 0 | 功能引导 |

> 全局字体: `"PingFang SC", -apple-system, "Noto Sans SC", sans-serif`

---

## 4. 效果系统

### 阴影

| Token | 值 | 用途 |
|-------|-----|------|
| shadow-soft | `0 2.55px 7.64px rgba(77,53,50,0.06)` | 按钮轻阴影 |
| shadow-md | `0 2px 4px -2px rgba(10,13,18,0.06), 0 4px 6px -1px rgba(10,13,18,0.1)` | Context Menu, Scroll to Bottom |
| shadow-2xl | `0 4px 4px -2px rgba(10,13,18,0.04), 0 24px 48px -12px rgba(10,13,18,0.18)` | Toast |
| shadow-3xl | `0 5px 5px -2.5px rgba(10,13,18,0.04), 0 32px 64px -12px rgba(10,13,18,0.14)` | Nav Bar 按钮, CTA 浮动 |
| shadow-card | `0 10px 15px rgba(53,46,38,0.3)` | 3D 角色图片 |
| avatar-inset | `inset 0 0 2.37px rgba(255,255,255,1)` | 星仔头像内光 |

### 模糊

| Token | 值 | 用途 |
|-------|-----|------|
| blur-md | `blur(16px)` | AI 气泡、Icon Button |
| blur-lg | `blur(24px)` | 用户气泡、导航栏 |
| blur-xl | `blur(40px)` | Name 底部面板 |
| blur-decorative | `blur(200px)` | 登录装饰光晕 |

---

## 5. 核心组件

### 5.1 Button 按钮

```
Component Set: "button" (1765:8114)

┌────────────┬──────────────────────┬──────────────────────┬──────────────────────┐
│            │ primary              │ secondary            │ disable              │
├────────────┼──────────────────────┼──────────────────────┼──────────────────────┤
│ L          │ bg:#7168D6 txt:白    │ bg:#EFEEFC b:#7168D6 │ bg:rgba(0,0,0,0.04)  │
│            │ 16px/500 p:12px 16px │ txt:#7168D6          │ txt:白               │
│ M          │ 同上 14px p:8px 16px │ 无bg b:#7168D6       │ bg:rgba(40,39,55,0.3)│
└────────────┴──────────────────────┴──────────────────────┴──────────────────────┘

公共: border-radius: 29px, width: hug

⚠️ Alert 中特殊:
  - 确认/危险: bg #F8837C, txt #F9F9FC
  - 取消: bg #E7E6ED, txt #282737
```

### 5.2 Icon Button 图标按钮

```
Component Set: "icon-button" (1765:8153)

┌──────┬───────────────────────────┬───────────────────────────┐
│      │ Default (深色)            │ Secondary (浅色)          │
│      │ bg: rgba(0,0,0,0.8)      │ bg: #F9F9FC               │
├──────┼───────────────────────────┼───────────────────────────┤
│ L    │ 56×56  icon:36  p:8px    │ 同                        │
│ M    │ 44×44  icon:28           │ 同                        │
│ S    │ 36×36  icon:20           │ 同                        │
└──────┴───────────────────────────┴───────────────────────────┘

公共: radius: 9999px, backdrop-filter: blur(16px), icon 白色
用途: L=万物皆有灵📷📞, M=日记CTA, S=关闭/返回
```

### 5.3 Small Button 小按钮

```
Component Set: "Small Button" (1765:8105)

icon: 透明底, 32×32, icon 26×26 品牌紫
fill: bg #7168D6, 32×32, icon 16×16 白色
disable: bg #D9D7F4, 同 fill
fill_s: bg rgba(0,0,0,0.8), 24×24, icon 16×16 白色

公共: radius 36px
用途: 发送按钮、Toast 关闭
```

### 5.4 Navigation Bar 导航栏

```
Component Set: "Navigation Bar" (1765:8127)
用于内页, 白底按钮 + shadow-3xl

Default: 仅右侧关闭按钮
  - row, justify-end, padding 12px 16px, width 393px
  - 按钮: bg #F9F9FC, radius 36px, p:8px, icon: lucide/x 20×20

Variant 2: 返回 + 居中标题 + 菜单
  - row, space-between
  - 左: Back (radius 999px, lucide/chevron-left)
  - 中: 标题 (Body 2/Regular, #282737, absolute 居中)
```

### 5.5 Top Bar 顶部导航

```
Component Set: "Top Bar" (1765:8173)
用于主页/聊天页, 渐变遮罩, position: absolute top

chat:     BG gradient(#D9D7F4 → transparent) opacity 80%
Variant4: 同 chat + 左上 expand 按钮 (36×36 #F9F9FC)
Variant2: 无 BG (简洁)
Dark:     BG gradient(rgba(40,39,55,0.5) → transparent)

公共: width 393px, row space-between center, p:12px 16px

独立组件 "Top Bar/home" (1765:8146):
  - gradient(#F8F5EF → transparent), 用于万物皆有灵/主页
```

### 5.6 Toast 提示

```
Component Set: "Toast" (1765:8056)
公共: bg #F9F9FC, radius 38px, shadow-2xl, row center, txt Body 3 #282737

Default:  icon:no_wifi  "网络无法连接..."  右:关闭按钮(32×32)
Variant2: icon:info     "遇到小状况..."    右:重试按钮
Variant4: icon:info     "最多三张图片"     右:关闭按钮
Variant3: icon:info     "手机号不正确"     无按钮, h:54px

关闭按钮: 32×32, bg #E7E6ED, radius 36px, icon 16×16
```

### 5.7 Alert 弹窗

```
Component: "Alert" (1765:8137)
width: 345px, bg #F9F9FC, radius 24px

结构: 标题区(p:32px 24px 24px) → 分隔线(1px border) → 按钮区(row gap:12px p:16px)
标题: Title 3/Medium 20px #282737 居中
按钮: 两个 fill 按钮 (取消 #E7E6ED + 确认 #F8837C)
```

### 5.8 Context Menu 上下文菜单

```
Component: "Contex Menu" (1765:8033)
width: 256px, bg #F9F9FC, radius 24px, shadow-md

结构: 操作行(3个 menu_button 52×64) → 分隔线 → emoji行(5个 44×44) → 尾部箭头
```

### 5.9 Scroll to Bottom

```
Component: "scroll to bottom" (1765:8030)
bg 白, radius 36px 0 0 36px, shadow-md, w:144px
icon: 20/down #7168D6 + "12 条新消息" Caption
固定屏幕右侧, 只露出左半部分
```

### 5.10 Chat Bubble 对话气泡

```
聊天容器: padding 16px 16px 16px 80px, gap 8px (同人) / 12px (切人)

AI 气泡 (fromMe=False):              用户气泡 (fromMe=True):
  bg: #F9F9FC                           bg: #EFEEFC
  border: 1px solid #FFFFFF             无边框
  radius: 20px 20px 20px 0             radius: 20px 20px 0 20px
  padding: 12px 16px                    padding: 12px 16px
  blur(16px), fill                      blur(24px), padding-left: 36px
  txt: #282737                          txt: #282737, 右对齐
```

### 5.11 Date / Cards / Bind Avatar

```
Date (1658:6778): row center, gap 8px, p:4px 8px, radius 10px

Cards: radius 0 20px 20px 20px, padding-right: 36px

Bind Avatar (×5 颜色): 用户头像 60×54 + 星仔 15.8×15.8 @ (40,38)
  星仔色: #987CFC / #F99F93 / #92E27C / #F8D8A8 / #C6B0FC
  边框: 1.68px #F8F8F8, inset 0 0 2.37px white
```

---

## 6. 页面结构

### 6.1 聊天页

```
┌─────────────────────────────────────┐
│ Status Bar (54px)                    │
│ Top Bar/chat (abs, gradient fade)    │
├─────────────────────────────────────┤
│ Chat Area (padding-left: 80px)       │
│   AI Bubble → 左对齐, fill          │
│   User Bubble → 右对齐, p-left 36px │
│   Task Card → radius 0 20 20 20     │
├─────────────────────────────────────┤
│ Action Bar                           │
│ [+ 告诉我任何事情...     ] [send]    │
│ "内容由 AI 生成"                     │
│ Home Indicator (34px)                │
└─────────────────────────────────────┘

背景: 全屏图片 chat-bg.png (394×852, stretch, 固定不滚动)
  含 3D 星仔(左下) + 木质墙壁(上半) + 地毯(下半)
```

### 6.2 任务管理页

```
背景: #F9F5EC, padding: 0 16px
Top Bar 标题: "亲子互动空间" (H4 20px center)
内容: Active → Recommend → Completed 三段列表
```

### 6.3 日记页

```
日记列表: bg #E7E6ED, Top Bar blur(24px), 1px bottom border
日记详情: bg #F9F9FC, CTA 浮动按钮 60×60 右下角 shadow-3xl
```

---

## 7. CSS 变量模板

```css
:root {
  /* 背景 */
  --bg-primary: #F8F5EF;
  --bg-white: #FFFFFF;
  --bg-component: #F9F9FC;
  --bg-muted: #E7E6ED;
  --bg-task: #F9F5EC;
  --bg-hero: #9CB9CA;
  --bg-intro: #F4ECE4;
  --bg-input: #F3F0E9;
  
  /* 品牌色 */
  --brand-purple-deep: #7168D6;
  --brand-purple: #987CFC;
  --brand-purple-light: #C6B0FC;
  --brand-purple-disabled: #D9D7F4;
  --brand-coral: #F8837C;
  --brand-pink: #EE8574;
  --brand-green: #92E27C;
  --brand-orange: #F99F93;
  --brand-gold: #F8D8A8;
  
  /* 渐变 */
  --gradient-purple: linear-gradient(180deg, #DBD8FF 0%, #EDEBFF 50%, #FFF 100%);
  --gradient-topbar-fade: linear-gradient(180deg, #F8F5EF 0%, rgba(248,245,239,0) 100%);
  --gradient-topbar-chat: linear-gradient(180deg, #D9D7F4 0%, transparent 100%);
  --gradient-topbar-dark: linear-gradient(180deg, rgba(40,39,55,0.5) 0%, rgba(40,39,55,0) 100%);
  --gradient-action-bar: linear-gradient(180deg, transparent 0%, #F4E8D7 100%);
  
  /* 文字 */
  --text-primary: #000000;
  --text-dark: #1D1D1F;
  --text-warm: #352E26;
  --text-gray: #424245;
  --text-bubble: #282737;
  --text-date: rgba(40, 39, 55, 0.3);
  --text-hint: rgba(53, 46, 38, 0.2);
  --text-border: rgba(0, 0, 0, 0.04);
  
  /* 字体 */
  --font-family: "PingFang SC", -apple-system, "Noto Sans SC", sans-serif;
  --font-large-title: 600 34px/1.3 var(--font-family);
  --font-title-1: 400 28px/1.4 var(--font-family);
  --font-title-3: 500 20px/1.4 var(--font-family);
  --font-h4: 500 20px/1.5 var(--font-family);
  --font-body-1: 500 17px/1.5 var(--font-family);
  --font-body: 400 16px/1.5 var(--font-family);
  --font-body-medium: 500 16px/1.5 var(--font-family);
  --font-body-3: 400 14px/1.35 var(--font-family);
  --font-body-lg: 500 24px/1.33 var(--font-family);
  --font-caption: 400 12px/1.3 var(--font-family);
  --letter-spacing: -0.01em;
  
  /* 气泡 */
  --bubble-bg-ai: #F9F9FC;
  --bubble-bg-user: #EFEEFC;
  --bubble-border-ai: 1px solid #FFFFFF;
  --bubble-padding: 12px 16px;
  --chat-offset-left: 80px;
  
  /* 组件色 */
  --btn-primary: #7168D6;
  --btn-secondary-bg: #EFEEFC;
  --btn-secondary-border: #7168D6;
  --btn-disable: rgba(0, 0, 0, 0.04);
  --btn-danger: #F8837C;
  --btn-muted: #E7E6ED;
  --icon-btn-dark: rgba(0, 0, 0, 0.8);
  --icon-btn-light: #F9F9FC;
  
  /* 圆角 */
  --radius-bubble-ai: 20px 20px 20px 0;
  --radius-bubble-user: 20px 20px 0 20px;
  --radius-card: 0 20px 20px 20px;
  --radius-card-inner: 16px;
  --radius-panel: 32px 32px 0 0;
  --radius-alert: 24px;
  --radius-toast: 38px;
  --radius-btn: 29px;
  --radius-full: 999px;
  
  /* 间距 */
  --space-page: 16px;
  --space-safe-bottom: 36px;
  --space-gap-cards: 12px;
  --space-gap-bubbles: 8px;
  
  /* 阴影 */
  --shadow-soft: 0 2.55px 7.64px rgba(77,53,50,0.06);
  --shadow-md: 0 2px 4px -2px rgba(10,13,18,0.06), 0 4px 6px -1px rgba(10,13,18,0.1);
  --shadow-2xl: 0 4px 4px -2px rgba(10,13,18,0.04), 0 24px 48px -12px rgba(10,13,18,0.18);
  --shadow-3xl: 0 5px 5px -2.5px rgba(10,13,18,0.04), 0 32px 64px -12px rgba(10,13,18,0.14);
  
  /* 模糊 */
  --blur-md: blur(16px);
  --blur-lg: blur(24px);
  --blur-xl: blur(40px);
  
  /* 尺寸 */
  --device-width: 393px;
  --device-height: 852px;
  --statusbar-height: 54px;
  --home-indicator: 34px;
}
```

---

## 8. Onboarding 页面系统

### 8.1 流程 & 公共布局

```
流程: Login → Intro(×2) → Q-Parent → Name → Voice → Q-BasicInfo
     → Q-Personality → Q-Goal → Q-Interest → Q-Input → Report → Home

公共模板:
┌─────────────────────────┐ 393×852
│ Status Bar + Top Bar     │ 114px (含返回 + Progress Bar)
│ Content Area (flexible)  │ padding: 0 16px
│ CTA 按钮                 │ padding: 0 32px, mb: 32px
└─────────────────────────┘

背景:
  大部分页面: gradient-purple (#DBD8FF → #EDEBFF → #FFF)
  BasicInfo: gradient-onboarding (#E4E3ED → #EFEEFC → #FCFBF9)
  Intro: solid #F4ECE4
```

### 8.2 Login 页

```
两段式: 上部展示区 + 下部操作区

上部: 居中 Avatar 圆框
  容器: 240×240, radius ∞, bg #F3F0E9, inset-shadow 0 0 36px white
  星仔 3D 图: 裁切显示在圆框内

下部: padding 0 32px 32px, gap 32px
  手机号 (Title 3 居中) → 一键登录(button/primary/L) → 其他登录(secondary)
  隐私复选框: Checkbox 20×20 + Caption 12px rgba(53,46,38,0.66)
```

### 8.3 Intro 介绍页

```
全屏沉浸式（无 Top Bar, 无 Progress Bar）, bg: #F4ECE4

主插画: 3D 渲染图 + gradient 遮罩(#E2D4EA → transparent)
标题: Large Title 34px/600 #1D1D1F "我是星仔，\n是孩子的聪明玩伴"
副文: Body 1 17px/500 #424245

Pagination Dots: 8×8, 激活 #FFF / 非激活 rgba(0,0,0,0.3)
CTA: "开始探索"
```

### 8.4 Question 问答页

```
通用结构: Top(返回+进度条) → Prompt(星仔头像+问题文字) → Options → CTA("下一步")

┌──────────────────┬───────────┬──────────┬─────────┐
│ 页面             │ 选项类型  │ 选择方式 │ 组件    │
├──────────────────┼───────────┼──────────┼─────────┤
│ Parent 家庭身份  │ 单行卡片  │ 单选     │ §9.2    │
│ BasicInfo 基本信息│ 表单      │ 输入     │ Segment │
│ Personality 性格 │ 双行卡片  │ 单选     │ §9.2    │
│ Goal 成长方向    │ 单行卡片  │ 多选     │ §9.2    │
│ Interest 兴趣    │ Tag 网格  │ 多选     │ §9.3    │
│ Input 自由输入   │ Textarea  │ 自由     │ -       │
└──────────────────┴───────────┴──────────┴─────────┘
```

### 8.5 Starfy Name & Voice

```
Name (取名页):
  上部: 孩子昵称(Title 1 28px) + "帮我起个名字吧!" + 星仔3D
  下部: 白色面板(radius 24px 24px 0 0, blur-xl), 输入框 + 提交按钮

Voice (音色选择):
  上部: 昵称 + "你希望我是哪个声音?" + 星仔3D
  下部: 2×3 网格, 每项 播放按钮(44×44 #7168D6) + 文字
  默认态: 白底 | 选中态: #7168D6 白字
  音色: 可爱, 直爽, 温暖, 阳光, 细腻, 积极
  CTA: "开始对话"
```

### 8.6 Report (共育邀请函)

```
长页面可滚动, bg gradient-purple
结构: 星仔头像 → 标题 → 引言 → "我眼中的XX" → "陪伴策略"×3 → "我会提供" → 底部
CTA: "带我去见糯糯"
```

---

## 9. Onboarding 专用组件

### 9.1 Progress Bar

```
左: Back button 28×28 radius ∞
右: 进度条(高4px, radius 999px, 填充 #7168D6)
总高: 114px (含 Status Bar), position: absolute top
```

### 9.2 Selection Card

```
单行: bg rgba(255,255,255,0.8), radius 16px, p:16px 20px
双行: 同上 + 副标题 Caption #666
选中: border 2px #7168D6 + ✓, gap 12px
```

### 9.3 Tag

```
默认: bg rgba(255,255,255,0.7), radius 999px, p:8px 16px, icon 24×24
选中: bg #7168D6, txt 白色
布局: 2 列居中, gap 12px
```

### 9.4 Privacy Alert / Gender Segment

```
Privacy: 遮罩 rgba(0,0,0,0.2)+blur(16px), Alert 345px rgba(255,255,255,0.85) radius 24px

Gender: 白框 radius 16px 两列, 每项 50% p:12px 16px radius 12px
  默认: 白底 #352E26 | 选中: #7168D6 白字
```

---

## 10. 万物皆有灵（语音互动页）

### 10.1 状态概览

```
1. 待机态: 全屏 3D 星仔 + 📷拍照 + 📞通话 按钮
2. 取景态: 暗色取景框(#19181B, 301×402, radius 24px) + 拍照按钮 + 挂断
3. 拍照完成: 照片预览 + ✕关闭 + 拍照 + 挂断
4. AI处理中: 照片模糊 + 魔法棒 + "魔法施展中..." + 重试按钮
5. AR全屏: 星仔叠加在实景照片上
```

### 10.2 页面结构

```
┌─────────────────────────────────────┐ 393×852
│ Top Bar/home (gradient fade)         │
├─────────────────────────────────────┤
│ 取景框: (46,54) 301×402              │
│   bg: #19181B, radius: 24px          │
│   ✕关闭(右上) + 📸拍照(底部居中)     │
│ 3D 星仔角色 (全屏背景图)             │
├─────────────────────────────────────┤
│ Action Bar                           │
│   bg: gradient(transparent→#F4E8D7)  │
│   opacity 60%, p:36px 32px 60px      │
│   待机: 📷(icon-btn/L/Sec) + 📞(L/Def)│
│   通话: 挂断(56×56 #F8837C radius ∞) │
│   "內容由 AI 生成" 10px rgba hint     │
└─────────────────────────────────────┘

背景: #9CB9CA, 全屏图 stretch
Top Bar: gradient(#F8F5EF → transparent)
```

---

## 11. 页面索引

| 模块 | DS 覆盖 | 章节 |
|------|---------|------|
| Onboarding (14屏) | ✅ 完成 | §8, §9 |
| 聊天（文字） | ✅ 完成 | §5.10, §6.1 |
| 万物皆有灵（语音, 5态） | ✅ 完成 | §10 |
| 通用组件 (15+) | ✅ 完成 | §5 |
| 任务管理 (7帧) | ⚠️ 骨架 | §6.2 |
| 日记 (6帧) | ⚠️ 骨架 | §6.3 |
| Profile (14帧) | ❌ 待补 | - |
| 模式切换 (4帧) | ⚠️ 部分 | - |
