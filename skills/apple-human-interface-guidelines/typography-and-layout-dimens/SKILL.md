---
name: "apple-human-interface-guidelines-typography"
description: "Apple HIG Typography和Layout映射到Android dimens规范。Invoke when implementing iOS-style UI in Android or designing UI that follows Apple HIG."
---

# Apple Human Interface Guidelines - Typography & Layout

本技能将Apple HIG Typography和Layout规范映射到Android开发环境，提供符合Apple设计语言的字体排版和布局系统。

## 核心原则

### 1. 可读性确保 (Ensuring Legibility)

- 使用大多数人可以轻松阅读的字体大小
- 遵循各平台的默认和最小字号规范
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

### 4. 支持Dynamic Type

- iOS/iPadOS/tvOS/visionOS/watchOS支持Dynamic Type
- 确保布局适配所有字体大小
- 图标随字体大小自动缩放（使用SF Symbols）
- 大字号时采用堆叠布局避免截断

## 平台字号规范参考

### 平台默认与最小字号

| 平台       | 默认字号 | 最小字号 |
|------------|----------|----------|
| iOS, iPadOS | 17pt    | 11pt     |
| macOS      | 13pt     | 10pt     |
| tvOS       | 29pt     | 23pt     |
| visionOS   | 17pt     | 12pt     |
| watchOS    | 16pt     | 12pt     |

### iOS Dynamic Type 尺寸表 (标准)

| Style       | Weight   | Size (pt) | Leading (pt) | Emphasized |
|-------------|----------|-----------|--------------|------------|
| Large Title | Regular  | 31        | 38           | Bold       |
| Title 1     | Regular  | 25        | 31           | Bold       |
| Title 2     | Regular  | 19        | 24           | Bold       |
| Title 3     | Regular  | 17        | 22           | Semibold   |
| Headline    | Semibold | 14        | 19           | Semibold   |
| Body        | Regular  | 14        | 19           | Semibold   |
| Callout     | Regular  | 13        | 18           | Semibold   |
| Subhead     | Regular  | 12        | 16           | Semibold   |
| Footnote    | Regular  | 12        | 16           | Semibold   |
| Caption 1   | Regular  | 11        | 13           | Semibold   |
| Caption 2   | Regular  | 11        | 13           | Semibold   |

### iOS Dynamic Type 尺寸表 (无障碍大字 AX1-AX5)

| Style       | Weight   | Size (pt) | Leading (pt) | Emphasized |
|-------------|----------|-----------|--------------|------------|
| Large Title | Regular  | 44        | 52           | Bold       |
| Title 1     | Regular  | 38        | 46           | Bold       |
| Title 2     | Regular  | 34        | 41           | Bold       |
| Title 3     | Regular  | 31        | 38           | Semibold   |
| Headline    | Semibold | 28        | 34           | Semibold   |
| Body        | Regular  | 28        | 34           | Semibold   |
| Callout     | Regular  | 26        | 32           | Semibold   |
| Subhead     | Regular  | 25        | 31           | Semibold   |
| Footnote    | Regular  | 23        | 29           | Semibold   |
| Caption 1   | Regular  | 22        | 28           | Semibold   |
| Caption 2   | Regular  | 20        | 25           | Semibold   |

### watchOS Dynamic Type 尺寸表

| Style       | Weight   | Size (pt) | Leading (pt) | Emphasized |
|-------------|----------|-----------|--------------|------------|
| Large Title | Regular  | 30        | 32.5         | Bold       |
| Title 1     | Regular  | 28        | 30.5         | Semibold   |
| Title 2     | Regular  | 24        | 26.5         | Semibold   |
| Title 3     | Regular  | 17        | 19.5         | Semibold   |
| Headline    | Semibold | 14        | 16.5         | Semibold   |
| Body        | Regular  | 14        | 16.5         | Semibold   |
| Caption 1   | Regular  | 13        | 15.5         | Semibold   |
| Caption 2   | Regular  | 12        | 14.5         | Semibold   |

## Android Dimen映射

### 基础字号系统 (基于Apple HIG)

```xml
<!-- Typography (SP) - Apple HIG Typography映射 -->
<!-- 参考: Apple HIG Typography Specifications -->
<!-- 使用Regular/Medium/Semibold/Bold字重，避免细字重用于小文本 -->

<!-- 主标题 -->
<dimen name="text_large_title">31sp</dimen>   <!-- Large Title: 31pt -->
<dimen name="text_title_1">25sp</dimen>       <!-- Title 1: 25pt -->
<dimen name="text_title_2">19sp</dimen>       <!-- Title 2: 19pt -->
<dimen name="text_title_3">17sp</dimen>       <!-- Title 3: 17pt -->

<!-- 正文 -->
<dimen name="text_headline">14sp</dimen>     <!-- Headline: 14pt semibold -->
<dimen name="text_body">14sp</dimen>         <!-- Body: 14pt -->
<dimen name="text_callout">13sp</dimen>       <!-- Callout: 13pt -->
<dimen name="text_subhead">12sp</dimen>      <!-- Subhead: 12pt -->

<!-- 辅助文本 -->
<dimen name="text_footnote">12sp</dimen>      <!-- Footnote: 12pt -->
<dimen name="text_caption_1">11sp</dimen>     <!-- Caption 1: 11pt -->
<dimen name="text_caption_2">11sp</dimen>     <!-- Caption 2: 11pt -->
```

### 无障碍大字 (AX1-AX5)

```xml
<!-- Accessibility Large Type Sizes -->
<dimen name="text_large_title_ax">44sp</dimen>   <!-- AX1: 44pt -->
<dimen name="text_title_1_ax">38sp</dimen>       <!-- AX2: 38pt -->
<dimen name="text_title_2_ax">34sp</dimen>      <!-- AX3: 34pt -->
<dimen name="text_title_3_ax">31sp</dimen>      <!-- AX4: 31pt -->
<dimen name="text_headline_ax">28sp</dimen>     <!-- AX1: 28pt -->
<dimen name="text_body_ax">28sp</dimen>         <!-- AX1: 28pt -->
```

### iOS风格别名

```xml
<!-- iOS Text Style Aliases -->
<dimen name="largeTitle">@dimen/text_large_title</dimen>  <!-- 31sp -->
<dimen name="title_1">@dimen/text_title_1</dimen>            <!-- 25sp -->
<dimen name="title_2">@dimen/text_title_2</dimen>            <!-- 19sp -->
<dimen name="title_3">@dimen/text_title_3</dimen>            <!-- 17sp -->
<dimen name="headline">@dimen/text_headline</dimen>          <!-- 14sp semibold -->
<dimen name="body">@dimen/text_body</dimen>                    <!-- 14sp -->
<dimen name="callout">@dimen/text_callout</dimen>              <!-- 13sp -->
<dimen name="subhead">@dimen/text_subhead</dimen>              <!-- 12sp -->
<dimen name="footnote">@dimen/text_footnote</dimen>              <!-- 12sp -->
<dimen name="caption_1">@dimen/text_caption_1</dimen>          <!-- 11sp -->
<dimen name="caption_2">@dimen/text_caption_2</dimen>              <!-- 11sp -->
```

### Android语义别名

```xml
<!-- Android Semantic Aliases -->
<dimen name="text_display">@dimen/text_large_title</dimen>
<dimen name="text_headline">@dimen/text_headline</dimen>
<dimen name="text_title">@dimen/text_title_3</dimen>
<dimen name="text_body">@dimen/text_body</dimen>
<dimen name="text_subhead">@dimen/text_subhead</dimen>
<dimen name="text_caption">@dimen/text_caption_1</dimen>
```

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

### 强调字重 (Emphasized)

使用 symbolic traits 显示强调变体:
- SwiftUI: `.bold()` modifier
- UIKit: `traitBold` in UIFontDescriptor

强调字重可以是: Medium, Semibold, Bold, Heavy

## 行高 (Leading) 映射

```xml
<!-- Leading (行高) - 基于Apple HIG -->
<dimen name="leading_large_title">38sp</dimen>   <!-- 31pt文字对应38pt行高 -->
<dimen name="leading_title_1">31sp</dimen>       <!-- 25pt -> 31pt -->
<dimen name="leading_title_2">24sp</dimen>       <!-- 19pt -> 24pt -->
<dimen name="leading_title_3">22sp</dimen>       <!-- 17pt -> 22pt -->
<dimen name="leading_headline">19sp</dimen>      <!-- 14pt -> 19pt -->
<dimen name="leading_body">19sp</dimen>          <!-- 14pt -> 19pt -->
<dimen name="leading_callout">18sp</dimen>       <!-- 13pt -> 18pt -->
<dimen name="leading_subhead">16sp</dimen>       <!-- 12pt -> 16pt -->
<dimen name="leading_footnote">16sp</dimen>       <!-- 12pt -> 16pt -->
<dimen name="leading_caption">13sp</dimen>       <!-- 11pt -> 13pt -->
```

## Android TextStyle定义

```xml
<!-- styles.xml -->
<style name="TextAppearance.App.LargeTitle" parent="TextAppearance.Material3.HeadlineLarge">
    <item name="android:textSize">@dimen/text_large_title</item>
    <item name="android:textColor">?attr/colorOnSurface</item>
    <item name="fontFamily">sans-serif</item>
</style>

<style name="TextAppearance.App.Title1" parent="TextAppearance.Material3.HeadlineMedium">
    <item name="android:textSize">@dimen/text_title_1</item>
    <item name="fontFamily">sans-serif</item>
</style>

<style name="TextAppearance.App.Title2" parent="TextAppearance.Material3.TitleLarge">
    <item name="android:textSize">@dimen/text_title_2</item>
    <item name="fontFamily">sans-serif</item>
</style>

<style name="TextAppearance.App.Title3" parent="TextAppearance.Material3.TitleMedium">
    <item name="android:textSize">@dimen/text_title_3</item>
    <item name="fontFamily">sans-serif-medium</item>
</style>

<style name="TextAppearance.App.Headline" parent="TextAppearance.Material3.TitleSmall">
    <item name="android:textSize">@dimen/text_headline</item>
    <item name="fontFamily">sans-serif-medium</item>
    <item name="android:textStyle">bold</item>
</style>

<style name="TextAppearance.App.Body" parent="TextAppearance.Material3.BodyMedium">
    <item name="android:textSize">@dimen/text_body</item>
    <item name="fontFamily">sans-serif</item>
</style>

<style name="TextAppearance.App.Caption" parent="TextAppearance.Material3.BodySmall">
    <item name="android:textSize">@dimen/text_caption_1</item>
    <item name="fontFamily">sans-serif</item>
</style>
```

## 字号选择指南

### 标题层级

| 场景       | 推荐字号        | 字重     |
|------------|-----------------|----------|
| 页面主标题 | 25-31sp (Large Title/Title 1) | Regular/Bold |
| 章节标题   | 17-25sp (Title 2-3)         | Regular/Semibold |
| 小标题     | 14-17sp (Headline/Title 3)   | Semibold |

### 正文内容

| 场景       | 推荐字号  | 字重     |
|------------|-----------|----------|
| 正文内容   | 14sp (Body) | Regular |
| 次要正文   | 12-13sp (Subhead/Callout) | Regular |
| 较长正文   | 14sp (Body) | Regular, leading 19sp |

### 辅助文本

| 场景       | 推荐字号   | 字重     |
|------------|------------|----------|
| 注释       | 12sp (Footnote) | Regular |
| Caption    | 11sp (Caption 1-2) | Regular |

## 使用场景

### 1. 列表项

- 主文本: Body (14sp, Regular)
- 次要文本: Footnote (12sp, Regular)
- 辅助信息: Caption (11sp, Regular)

### 2. 卡片

- 标题: Title 3 (17sp, Semibold)
- 内容: Body (14sp, Regular)
- 元数据: Caption (11sp, Regular)

### 3. 按钮

- 主按钮文字: 14sp, Medium
- 次要按钮: 12sp, Regular

### 4. 导航

- 底部导航: 12sp, Regular
- Tab文字: 14sp, Medium

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

| 场景             | 推荐间距          |
|------------------|-------------------|
| 组件内部小间距   | space_0_5x (4dp)  |
| 组件之间标准间距 | space_1x (8dp)    |
| 列表项间距       | space_1_5x (12dp)  |
| 卡片内边距       | space_2x (16dp)   |
| 区块之间         | space_3x (24dp)   |
| 页面大区块       | space_4x (32dp)   |

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

| 场景               | 圆角值                 |
|--------------------|-----------------------|
| 圆形按钮/头像       | radius_round_full (512dp) |
| 卡片/按钮          | radius_m (12dp)       |
| 大圆角容器         | radius_l (24dp)       |
| 分割线粗细         | stroke_width_default (3dp) |

### 3. 布局高度系统 (Layout Height)

```xml
<!-- Layout height system -->
<dimen name="layout_height_xs">30dp</dimen>
<dimen name="layout_height_s">40dp</dimen>
<dimen name="layout_height_m">48dp</dimen>
<dimen name="layout_height_l">56dp</dimen>
<dimen name="layout_height_xl">64dp</dimen>
<dimen name="layout_height_xxl">96dp</dimen>
```

### 高度选择指南

| 场景               | 高度                |
|--------------------|---------------------|
| 单行小元素         | layout_height_s (40dp) |
| 标准列表项         | layout_height_m (48dp) |
| 大列表项/按钮      | layout_height_l (56dp) |
| 顶部/底部栏        | layout_height_xl (64dp) |
| 大区块容器         | layout_height_xxl (96dp) |

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

## 响应式布局注意事项

1. **安全区域**: 使用WindowInsetsCompat处理安全区域
2. **Size Class**: iPad横屏使用Regular宽高，iPhone竖屏使用Compact宽
3. **Grid**: tvOS根据屏幕宽度自动调整列数
4. **断点**: 组件在小屏使用紧凑间距，大屏使用宽松间距
5. **大字号适配**: 长文本使用多行显示，避免截断，考虑堆叠布局

## 快速参考表

### Typography

| Apple Style    | Android Dimen      | 推荐用途     |
|----------------|--------------------|--------------|
| Large Title    | text_large_title  | 页面主标题   |
| Title 1        | text_title_1       | 章节标题     |
| Title 2        | text_title_2       | 章节标题     |
| Title 3        | text_title_3       | 小标题       |
| Headline       | text_headline      | 列表项标题   |
| Body           | text_body          | 正文内容     |
| Callout        | text_callout       | 辅助说明     |
| Subhead        | text_subhead       | 次要文本     |
| Footnote       | text_footnote      | 注释/时间戳  |
| Caption 1/2    | text_caption_1     | 最小辅助信息 |

### Layout

| 场景             | 推荐尺寸              |
|------------------|-----------------------|
| 标准间距         | space_1x (8dp)        |
| 卡片内边距       | space_2x (16dp)       |
| 卡片圆角         | radius_m (12dp)        |
| 标准图标         | icon_m_24 (24dp)       |
| 列表项高度       | layout_height_m (48dp) |
| 按钮高度         | layout_height_l (56dp) |

## 注意事项

1. **避免硬编码字号**: 始终使用dimen资源
2. **一致性**: 整个应用使用统一的字号层级
3. **可访问性**: 考虑用户偏好字体大小，提供Dynamic Type支持
4. **字重匹配**: 标题和正文使用匹配的字重系统
5. **行高**: 根据字号调整行高，大字号使用相对较小的行高比
6. **响应式**: 大字号时调整布局，避免截断和重叠
