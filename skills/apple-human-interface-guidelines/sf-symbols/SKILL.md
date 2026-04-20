---
name: "apple-human-interface-guidelines-sf-symbols"
description: "SF Symbols图标系统，包含渲染模式、权重、动画。Invoke when using SF Symbols or designing custom symbols."
---

# iOS SF Symbols - SF 符号系统

基于 Apple Human Interface Guidelines 的 SF Symbols 设计规范。

## 概述

### 用途

- 工具栏、标签栏、上下文菜单、文本中的图标
- 跨 Apple 平台一致

### 版本注意

- 特定年份引入的符号和功能在早期系统不可用
- 访问 SF Symbols app 浏览完整符号集

---

## 渲染模式

### 四种模式

| 模式 | 描述 |
|------|------|
| Monochrome | 单色，应用一种颜色 |
| Hierarchical | 层次，同色不同透明度 |
| Palette | 调色板，每层不同颜色 |
| Multicolor | 多色，固有颜色 |

### 图层结构

- Primary：主要元素
- Secondary：次要元素
- Tertiary：辅助元素

---

## 渐变与变量颜色

### 渐变 (SF Symbols 7+)

- 从单一颜色生成线性渐变
- 适合大尺寸

### 变量颜色

- 表示随时间变化的特征（容量、强度）
- 不同阈值应用不同层颜色
- 用于进度、状态指示

---

## 权重与缩放

### 权重等级

Ultralight, Thin, Light, Regular, Medium, Semibold, Bold, Heavy, Black

### 缩放

- Small（小）
- Medium（默认）
- Large（大）

### 用途

- 与相邻文字权重匹配
- 调整强调程度

---

## 变体

### 设计变体

| 变体 | 描述 |
|------|------|
| Outline | 轮廓（最常见）|
| Fill | 填充 |
| Slash | 斜线（禁用状态）|
| Circle | 圆形包裹 |
| Square | 方形包裹 |
| Rectangle | 矩形包裹 |

### 语言变体

- 拉丁文、阿拉伯文、希伯来文、印地文、中文、日文、韩文等
- 自动适配设备语言

---

## 动画

### 动画类型

| 动画 | 描述 |
|------|------|
| Appear | 渐入 |
| Disappear | 渐出 |
| Bounce | 弹跳 |
| Scale | 缩放 |
| Pulse | 脉冲 |
| Variable Color | 变量颜色 |
| Replace | 替换 |
| Magic Replace | 智能替换 |
| Wiggle | 摇摆 |
| Breathe | 呼吸 |
| Rotate | 旋转 |
| Draw On/Off | 绘制 |

### 使用原则

- 谨慎使用
- 服务明确目的
- 提升信息传达效率
- 匹配应用调性

---

## 自定义符号

### 创建流程

1. 导出相似符号模板
2. 使用矢量编辑工具修改

### 设计原则

- 简洁
- 可识别
- 包容性
- 与动作或内容直接相关

### 标注

- 分配颜色或层级
- 支持所有渲染模式

### 负边距

- 辅助光学对齐
- 命名遵循规范

---

## Android 适配

### 等价方案

Android 使用 Material Icons 作为等价。

```xml
<!-- Material Icons -->
<ImageView
    android:src="@drawable/ic_add"
    app:tint="@color/icon_tint" />
```

### 图标集

| SF Symbols | Material Icons |
|------------|---------------|
| checkmark | ic_check |
| xmark | ic_close |
| plus | ic_add |
| trash | ic_delete |
| pencil | ic_edit |
| magnifyingglass | ic_search |
| person.crop.circle | ic_person |
| gear | ic_settings |
| house | ic_home |
| star | ic_star |

### Compose 图标

```kotlin
// Material Icons in Compose
Icon(
    imageVector = Icons.Default.Add,
    contentDescription = "Add",
    tint = Color.Blue
)
```

### 自定义图标

```xml
<!-- 自定义矢量图标 -->
<vector xmlns:android="http://schemas.android.com/apk/res/android"
    android:width="24dp"
    android:height="24dp"
    android:viewportWidth="24"
    android:viewportHeight="24">
    <path
        android:fillColor="#007AFF"
        android:pathData="M12,2C6.48,2 2,6.48 2,12s4.48,10 10,10 10,-4.48 10,-10S17.52,2 12,2z"/>
</vector>
```
