---
name: "apple-human-interface-guidelines-typography"
description: "Apple HIG Typography和Layout映射到Android dimens规范。Invoke when implementing iOS-style UI in Android or designing UI that follows Apple HIG."
---

# Apple Human Interface Guidelines - Typography & Layout

本技能将Apple HIG Typography和Layout规范映射到Android开发环境，提供符合Apple设计语言的字体排版和布局系统。

## 核心原则

### 1. 可读性确保 (Ensuring Legibility)
- 使用大多数人可以轻松阅读的字体大小
- 避免使用Light、Thin、Ultralight等细字重，优先使用Regular、Medium、Semibold、Bold
- 自定义字体如使用细字重，需增大字号以提高可读性

### 2. 层级传达 (Conveying Hierarchy)
- 通过字体粗细、大小、颜色强调重要信息
- 最小化使用字体数量，过多字体类型会混淆信息层级
- 调整重要内容优先级以响应文本大小变化

### 3. 系统字体优先 (Using System Fonts)
- iOS/iPadOS/tvOS/visionOS: SF Pro (无衬线)
- macOS: SF Pro
- watchOS: SF Compact (SF Compact Rounded用于复杂功能)
- NY: 衬线字体，与SF配合使用

## Android Dimen映射

### 基础字号系统 (基于Apple HIG)

```xml
<!-- Typography (SP) - Apple HIG Typography映射 -->
<!-- 参考: Apple HIG typography legibility and hierarchy -->
<!-- 使用Regular/Medium/Semibold/Bold字重，避免细字重用于小文本 -->

<dimen name="text_display_l">22sp</dimen>    <!-- Large Title级别 -->
<dimen name="text_title_l">20sp</dimen>      <!-- Title 1 -->
<dimen name="text_title_m">18sp</dimen>      <!-- Title 2-3 -->
<dimen name="text_body_l">17sp</dimen>       <!-- Body Large -->
<dimen name="text_body_m">16sp</dimen>       <!-- Body / Headline -->
<dimen name="text_body_s">14sp</dimen>       <!-- Subheadline -->
<dimen name="text_note_m">12sp</dimen>       <!-- Footnote / Caption -->
<dimen name="text_note_s">11sp</dimen>       <!-- Caption 2 -->
<dimen name="text_caption">10sp</dimen>     <!-- 最小字号 -->
```

### iOS风格别名

```xml
<!-- iOS风格别名 (iOS Text Style Aliases) -->
<dimen name="largeTitle">@dimen/text_title_l</dimen>   <!-- 22sp -> 20sp -->
<dimen name="title">@dimen/text_body_m</dimen>        <!-- 17pt -> 16sp -->
<dimen name="headline">@dimen/text_body_m</dimen>      <!-- 14pt semibold -> 16sp semibold -->
<dimen name="body">@dimen/text_body_m</dimen>           <!-- 17pt -> 16sp -->
<dimen name="subhead">@dimen/text_body_s</dimen>       <!-- 15pt -> 14sp -->
<dimen name="footnote">@dimen/text_note_m</dimen>        <!-- 13pt -> 12sp -->
<dimen name="caption">@dimen/text_caption</dimen>       <!-- 12pt -> 10sp -->
```

### Android语义别名

```xml
<!-- Android语义别名 (Android Semantic Aliases) -->
<dimen name="large_text_size">@dimen/largeTitle</dimen>
<dimen name="medium_bold_text_size">@dimen/headline</dimen>
<dimen name="medium_text_size">@dimen/body</dimen>
<dimen name="small_text_size">@dimen/subhead</dimen>
<dimen name="medium_subtext_size">@dimen/footnote</dimen>
<dimen name="small_subtext_size">@dimen/caption</dimen>
```

## 平台字号规范参考

### iOS/iPadOS 默认与最小字号

| 平台 | 默认字号 | 最小字号 |
|------|----------|----------|
| iOS, iPadOS | 17pt | 11pt |
| macOS | 13pt | 10pt |
| tvOS | 29pt | 23pt |
| visionOS | 17pt | 12pt |
| watchOS | 16pt | 12pt |

### iOS Dynamic Type 尺寸表

| Style | Weight | Size (pt) | Leading (pt) | Emphasized |
|-------|--------|------------|--------------|------------|
| Large Title | Regular | 31 | 38 | Bold |
| Title 1 | Regular | 25 | 31 | Bold |
| Title 2 | Regular | 19 | 24 | Bold |
| Title 3 | Regular | 17 | 22 | Semibold |
| Headline | Semibold | 14 | 19 | Semibold |
| Body | Regular | 14 | 19 | Semibold |
| Callout | Regular | 13 | 18 | Semibold |
| Subhead | Regular | 12 | 16 | Semibold |
| Footnote | Regular | 12 | 16 | Semibold |
| Caption 1 | Regular | 11 | 13 | Semibold |
| Caption 2 | Regular | 11 | 13 | Semibold |

## 字号选择指南

### 标题层级
- **主标题 (Large Title)**: 20-22sp, Bold
- **章节标题 (Title 1-3)**: 18-20sp, Regular/Semibold
- **小标题**: 16sp, Medium/Semibold

### 正文内容
- **正文 (Body)**: 14-16sp, Regular
- **次要正文**: 14sp, Regular

### 辅助文本
- **注释 (Footnote)**: 12sp, Regular
- **Caption**: 10-11sp, Regular

## 字重使用规范

### 推荐字重
- Regular (常规)
- Medium (中等)
- Semibold (半粗体)
- Bold (粗体)

### 避免使用
- Ultralight
- Thin
- Light

原因: 细字重在小字号时难以辨认，影响可读性。

## Android TextStyle定义

```xml
<!-- styles.xml -->
<style name="TextAppearance.App.LargeTitle" parent="TextAppearance.Material3.HeadlineLarge">
    <item name="android:textSize">@dimen/text_display_l</item>
    <item name="android:fontFamily">sans-serif</item>
    <item name="fontFamily">sans-serif</item>
</style>

<style name="TextAppearance.App.Title" parent="TextAppearance.Material3.TitleMedium">
    <item name="android:textSize">@dimen/text_title_m</item>
    <item name="android:fontFamily">sans-serif-medium</item>
</style>

<style name="TextAppearance.App.Body" parent="TextAppearance.Material3.BodyMedium">
    <item name="android:textSize">@dimen/text_body_m</item>
    <item name="android:fontFamily">sans-serif</item>
</style>

<style name="TextAppearance.App.Caption" parent="TextAppearance.Material3.BodySmall">
    <item name="android:textSize">@dimen/text_caption</item>
    <item name="android:fontFamily">sans-serif</item>
</style>
```

## 使用场景

### 1. 列表项
- 主文本: Body (16sp, Regular)
- 次要文本: Footnote (12sp, Regular)
- 辅助信息: Caption (10sp, Regular)

### 2. 卡片
- 标题: Title (18sp, Semibold)
- 内容: Body (16sp, Regular)
- 元数据: Caption (10sp, Regular)

### 3. 按钮
- 主按钮文字: 16sp, Medium
- 次要按钮: 14sp, Regular

### 4. 导航
- 底部导航: 12sp, Regular
- Tab文字: 14sp, Medium

## 响应式设计考虑

### 大字号适配
- 当用户系统字体放大时，考虑布局适应性
- 避免在受限空间使用固定高度文本容器
- 长文本使用多行显示，避免截断

### 语义化命名
使用语义化的dimen名称，便于维护和理解:
- `text_title_primary` 而非 `text_20sp`
- `text_body_regular` 而非 `text_16sp`

## 注意事项

1. **避免硬编码字号**: 始终使用dimen资源
2. **一致性**: 整个应用使用统一的字号层级
3. **可访问性**: 考虑用户偏好字体大小，提供适当支持
4. **字重匹配**: 标题和正文使用匹配的字重系统
5. **行高**: 根据字号调整行高，大字号使用相对较小的行高比

## 快速参考表

| Apple Style | Android Dimen | 推荐用途 |
|-------------|---------------|----------|
| Large Title | text_display_l | 页面主标题 |
| Title 1-2 | text_title_l/m | 章节标题 |
| Headline | text_body_m | 列表项标题 |
| Body | text_body_m/s | 正文内容 |
| Subhead | text_body_s | 辅助说明 |
| Footnote | text_note_m | 注释/时间戳 |
| Caption | text_caption | 最小辅助信息 |

---

## 布局系统 (Layout System)

基于Apple HIG Layout规范和实际dimens.xml实现。

### 1. 间距系统 (Spacing)

基础网格: 8dp

```xml
<!-- Spacing system (base = 8dp) -->
<dimen name="space_0">0dp</dimen>
<dimen name="space_0_5x">4dp</dimen>
<dimen name="space_1x">8dp</dimen>
<dimen name="space_1_5x">12dp</dimen>
<dimen name="space_2x">16dp</dimen>
<dimen name="space_3x">24dp</dimen>
<dimen name="space_4x">32dp</dimen>
<dimen name="space_5x">40dp</dimen>
<dimen name="space_6x">48dp</dimen>
<dimen name="space_8x">64dp</dimen>
```

### 间距使用指南

| 场景 | 推荐间距 |
|------|----------|
| 组件内部小间距 | space_0_5x (4dp) |
| 组件之间标准间距 | space_1x (8dp) |
| 列表项间距 | space_1_5x (12dp) |
| 卡片内边距 | space_2x (16dp) |
| 区块之间 | space_3x (24dp) |
| 页面大区块 | space_4x (32dp) |

### 2. 圆角与描边 (Radius & Stroke)

```xml
<!-- Radius and stroke -->
<dimen name="radius_round_full">512dp</dimen>
<dimen name="radius_m">12dp</dimen>
<dimen name="radius_l">24dp</dimen>
<dimen name="stroke_width_default">3dp</dimen>
<dimen name="elevation_bottom_navigation_bar">8dp</dimen>
```

### 圆角使用场景

| 场景 | 圆角值 |
|------|--------|
| 圆形按钮/头像 | radius_round_full (512dp) |
| 卡片/按钮 | radius_m (12dp) |
| 大圆角容器 | radius_l (24dp) |
| 分割线粗细 | stroke_width_default (3dp) |

### 3. 布局高度系统 (Layout Height)

```xml
<!-- Layout height system (for list / flow adaptive layouts) -->
<dimen name="layout_height_xs">30dp</dimen>
<dimen name="layout_height_s">40dp</dimen>
<dimen name="layout_height_m">48dp</dimen>
<dimen name="layout_height_l">56dp</dimen>
<dimen name="layout_height_xl">64dp</dimen>
<dimen name="layout_height_xxl">96dp</dimen>
```

### 高度选择指南

| 场景 | 高度 |
|------|------|
| 单行小元素 | layout_height_s (40dp) |
| 标准列表项 | layout_height_m (48dp) |
| 大列表项/按钮 | layout_height_l (56dp) |
| 顶部/底部栏 | layout_height_xl (64dp) |
| 大区块容器 | layout_height_xxl (96dp) |

### 4. 图标尺寸系统 (Icon Size)

```xml
<!-- Icon size system -->
<dimen name="icon_xs_16">16dp</dimen>
<dimen name="icon_s_20">20dp</dimen>
<dimen name="icon_m_24">24dp</dimen>
<dimen name="icon_l_32">32dp</dimen>
<dimen name="icon_xl_40">40dp</dimen>
<dimen name="icon_xxl_48">48dp</dimen>
<dimen name="icon_display_60">60dp</dimen>
```

### 图标使用场景

| 场景 | 尺寸 |
|------|------|
| 辅助图标/徽标 | icon_xs_16 (16dp) |
| 行内图标 | icon_s_20 (20dp) |
| 标准图标 | icon_m_24 (24dp) |
| 大图标 | icon_l_32 (32dp) |
| 展示图标 | icon_xl_40 (40dp) |

### 5. 头像尺寸系统 (Avatar Size)

```xml
<!-- Avatar size system -->
<dimen name="avatar_xs_24">24dp</dimen>
<dimen name="avatar_s_32">32dp</dimen>
<dimen name="avatar_m_40">40dp</dimen>
<dimen name="avatar_l_48">48dp</dimen>
<dimen name="avatar_xl_64">64dp</dimen>
<dimen name="avatar_xxl_80">80dp</dimen>
<dimen name="avatar_display_96">96dp</dimen>
```

### 头像使用场景

| 场景 | 尺寸 |
|------|------|
| 列表内小头像 | avatar_xs_24 (24dp) |
| 标准列表头像 | avatar_s_32 (32dp) |
| 详情页头像 | avatar_m_40 (40dp) |
| 个人资料头像 | avatar_l_48 (48dp) |
| 大展示头像 | avatar_xl_64 (64dp) |

## Apple HIG Layout 核心原则

### 1. 视觉层级 (Visual Hierarchy)
- 通过负空间、背景形状、颜色区分元素关联性
- 重要信息给予足够空间便于查找
- 内容延伸至屏幕边缘

### 2. 对齐 (Alignment)
- 组件对齐便于扫描和理解组织结构
- 配合缩进传达信息层级

### 3. 间距 (Spacing)
- 控制周围空间足够便于使用
- 将相关控件分组到逻辑区域

### 4. 适配性 (Adaptability)
- 尊重系统安全区域、边距和引导线
- 支持横竖屏切换
- 支持Dynamic Type文字大小变化

## 平台布局规范

### iOS
- 全屏显示填充到边缘
- 滚动布局延续到屏幕底部和侧边
- 按钮避免全宽，使用系统边距

### tvOS
- 内容距屏幕边缘: 上下60pt，左右80pt
- 焦点元素间距避免重叠

### visionOS
- 交互组件中心至少60pt间隔
- 内容保持在窗口边界内

### watchOS
- 内容从屏幕一边延伸到另一边
- 避免超过2-3个并排控件

## 组件布局模板

### 列表项布局
```
[头像/图标] [主标题]          [辅助信息]
space_1x    space_2x         space_2x
```

### 卡片布局
```
[图片]
[标题]                    space_1_5x
[副标题/描述]              space_1x
[底部按钮/元数据]          space_2x
```

### 表单布局
```
[标签]                    space_1x
[输入框]                  space_2x
[错误提示]                space_0_5x
```

## 响应式布局注意事项

1. **安全区域**: 使用WindowInsetsCompat处理安全区域
2. **Size Class**: iPad横屏使用Regular宽高，iPhone竖屏使用Compact宽
3. **Grid**: tvOS根据屏幕宽度自动调整列数
4. **断点**: 组件在小屏使用紧凑间距，大屏使用宽松间距
