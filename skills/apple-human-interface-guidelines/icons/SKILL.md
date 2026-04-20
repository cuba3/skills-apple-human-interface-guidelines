---
name: "apple-human-interface-guidelines-icons"
description: "iOS图标设计规范，包含SF Symbols使用、视觉一致性、光学对齐。Invoke when designing interface icons or using SF Symbols."
---

# iOS Icons - 图标设计指南

基于 Apple Human Interface Guidelines 的界面图标设计规范。

## 核心原则

### 简洁设计

- 可识别、高度简化
- 避免过多细节
- 使用熟悉视觉隐喻
- 与动作或内容直接相关

### 视觉一致性

- 统一尺寸
- 统一细节层级
- 统一线条粗细/字重
- 统一视角

---

## SF Symbols 使用

### 常用符号示例

| 类别 | 符号名 | 用途 |
|------|--------|------|
| 编辑 | scissors | 剪切 |
| 编辑 | doc.on.doc | 复制 |
| 编辑 | doc.on.clipboard | 粘贴 |
| 编辑 | checkmark | 完成 |
| 编辑 | xmark | 关闭/删除 |
| 编辑 | trash | 删除 |
| 编辑 | arrow.uturn.backward | 撤销 |
| 编辑 | arrow.uturn.forward | 重做 |
| 选择 | checkmark.circle | 选中 |
| 搜索 | magnifyingglass | 搜索 |
| 分享 | square.and.arrow.up | 分享 |
| 用户 | person.crop.circle | 账户 |
| 评分 | hand.thumbsup | 点赞 |
| 评分 | hand.thumbsdown | 差评 |
| 导航 | chevron.right | 前进 |
| 导航 | chevron.left | 后退 |

### 渲染模式

- **Monochrome**: 单色
- **Hierarchical**: 层次（不同透明度）
- **Palette**: 调色板（多色）
- **Multicolor**: 多色（固有颜色）

### 变体

- **Fill**: 填充
- **Outline**: 轮廓
- **Slash**: 斜线（禁用状态）
- **Circle/Square/Rectangle**: 圆形/方形/矩形包裹

### 字重等级

Ultralight, Thin, Light, Regular, Medium, Semibold, Bold, Heavy, Black

### 缩放

Small, Medium (默认), Large

---

## 设计要点

### 光学对齐

- 非对称图标可能需要调整位置
- 视觉中心而非几何中心
- 使用padding微调

### 选中状态

- 标准系统组件自动处理
- 自定义图标提供选中版本
- 选中时使用强调色

### 包容性

- 使用性别中立人物图像
- 避免文化特定图像

### 文字处理

- 仅在必要时包含文字
- 需要本地化
- RTL语言需要翻转版本

### 无障碍

- 提供替代文字标签
- VoiceOver 描述

---

## Android 适配

### 矢量图标

```xml
<!-- drawable/ic_menu.xml -->
<vector xmlns:android="http://schemas.android.com/apk/res/android"
    android:width="24dp"
    android:height="24dp"
    android:viewportWidth="24"
    android:viewportHeight="24">
    <path
        android:fillColor="#007AFF"
        android:pathData="M3,18h18v-2H3v2zm0-5h18v-2H3v2zm0-7v2h18V6H3z"/>
</vector>
```

### 图标尺寸

| 场景 | 尺寸 |
|------|------|
| 小图标 | 16dp (icon_xs_16) |
| 行内图标 | 20dp (icon_s_20) |
| 标准图标 | 24dp (icon_m_24) |
| 大图标 | 32dp (icon_l_32) |
| 展示图标 | 40dp (icon_xl_40) |

### 颜色适配

```xml
<!-- 白天模式 -->
<color name="icon_tint">#007AFF</color>

<!-- 夜间模式 -->
<color name="icon_tint">#0A84FF</color>
```

### 使用方式

```xml
<ImageView
    android:src="@drawable/ic_menu"
    android:tint="@color/icon_tint" />

<!-- 或使用 app:tint -->
<ImageView
    app:srcCompat="@drawable/ic_menu"
    app:tint="@color/icon_tint" />
```
