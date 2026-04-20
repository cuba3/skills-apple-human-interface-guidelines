---
name: "apple-human-interface-guidelines-dark-mode"
description: "iOS深色模式设计规范，包含配色方案、对比度要求。Invoke when implementing Dark Mode in iOS/Android app."
---

# iOS Dark Mode - 深色模式设计指南

基于 Apple Human Interface Guidelines 的深色模式设计规范。

## 核心原则

### 基础要求

- 不要提供应用内单独的深色模式设置
- 确保应用在两种模式下都好看
- 使用系统定义颜色确保适配性

### 不支持平台

- visionOS：不支持深色模式
- watchOS：不支持深色模式

---

## 配色方案

### 深色模式特点

- 背景色更暗
- 前景色更亮
- 不是简单的颜色反转

### iOS/iPadOS 层级

- Base (基础)：更暗，让背景界面后退
- Elevated (提升)：更亮，让前景界面前进

### 使用系统背景色

- 动态变化：背景自动从base转为elevated
- 多任务环境自动分离
- 避免自定义背景色

---

## 对比度要求

### 最低标准

- 最小对比度：4.5:1
- 推荐对比度：7:1（小文本）
- 使用系统颜色自动满足

### 检查清单

- 白天模式检查
- 夜间模式检查
- Increase Contrast 开启时检查
- Reduce Transparency 开启时检查

---

## 元素适配

### 图标与图片

- 使用SF Symbols（自动适配）
- 需要时提供深色/浅色版本
- 测试两种模式下的可见性

### 文字

- 使用系统标签颜色
- Primary/Secondary/Tertiary/Quaternary
- 使用系统视图显示文本

### 其他元素

- 分割线
- 填充色
- 边框

---

## Android 适配

### 资源目录

```
res/
  values/colors.xml      # 白天模式
  values-night/colors.xml # 夜间模式
```

### 定义方式

```xml
<!-- values/colors.xml -->
<color name="background">#FFFFFF</color>
<color name="surface">#F2F2F7</color>
<color name="on_background">#000000</color>
<color name="on_surface">#000000</color>

<!-- values-night/colors.xml -->
<color name="background">#000000</color>
<color name="surface">#1C1C1E</color>
<color name="on_background">#FFFFFF</color>
<color name="on_surface">#FFFFFF</color>
```

### 主题适配

```xml
<!-- values/themes.xml -->
<style name="AppTheme" parent="Theme.MaterialComponents.DayNight.NoActionBar">
    <item name="android:colorBackground">@color/background</item>
    <item name="colorSurface">@color/surface</item>
    <item name="colorOnBackground">@color/on_background</item>
    <item name="colorOnSurface">@color/on_surface</item>
</style>
```

### 强制深色

```xml
<!-- 强制深色主题 -->
<style name="AppTheme.Dark" parent="Theme.MaterialComponents.NoActionBar">
    <item name="android:theme">@style/AppTheme.Dark</item>
</style>
```

### 系统设置监听

```kotlin
// 检测系统深色模式
val darkModeEnabled = resources.configuration.uiMode and 
    Configuration.UI_MODE_NIGHT_MASK == Configuration.UI_MODE_NIGHT_YES
```
