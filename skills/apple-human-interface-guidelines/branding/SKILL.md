---
name: "apple-human-interface-guidelines-branding"
description: "iOS品牌设计指南，包含品牌色调、字体、logo使用规范。Invoke when implementing branding in iOS/Android app."
---

# iOS Branding - 品牌设计指南

基于 Apple Human Interface Guidelines 的品牌设计规范。

## 核心原则

### 品牌声音与调性

- 使用平实语言
- 适当使用感叹号和emoji
- 简洁句子结构
- 传达鼓励和乐观的感觉

### 强调色

- 指定应用元素（图标、按钮、文字）的强调色
- macOS用户可选择自己的强调色

### 自定义字体

- 确保字体在所有尺寸下可读
- 支持粗体和更大字号
- 标题/副标题可用自定义字体
- 正文/ Caption 使用系统字体（为小字号优化）

---

## 设计要点

### 内容优先

- 品牌元素不应抢占内容空间
- 采用精致、不显眼的方式融入品牌
- 不要用品牌资产填满整个屏幕

### 使用标准模式

- UI组件放在预期位置
- 使用标准符号表示常见操作
- 保持熟悉的行为

### Logo使用

- 除非必要提供上下文，否则避免显示logo
- 用户知道自己使用什么应用

### 启动屏幕

- 避免用作品牌展示
- 显示太快无法传达信息
- 可考虑欢迎/引导屏幕

### Apple商标

- 不得出现在应用名称或图片中
- 遵循Apple商标使用指南

---

## Android 适配

### 强调色

```xml
<!-- colors.xml -->
<color name="brand_primary">#007AFF</color>
<color name="brand_accent">#FF2D55</color>

<!-- 使用时引用 -->
<item name="colorPrimary">@color/brand_primary</item>
<item name="colorAccent">@color/brand_accent</item>
```

### 主题定义

```xml
<!-- themes.xml -->
<style name="AppTheme" parent="Theme.MaterialComponents">
    <item name="colorPrimary">@color/brand_primary</item>
    <item name="colorPrimaryVariant">@color/brand_primary_dark</item>
    <item name="colorOnPrimary">@color/white</item>
    <item name="colorSecondary">@color/brand_accent</item>
</style>
```

### 自定义字体

```xml
<!-- fonts.xml -->
<font-family xmlns:app="http://schemas.android.com/apk/res-auto">
    <font
        app:font="@font/brand_font_bold"
        app:fontStyle="normal"
        app:fontWeight="700" />
</font-family>
```
