---
name: "apple-human-interface-guidelines-materials"
description: "iOS材质设计规范，包含Liquid Glass、系统材质、模糊效果。Invoke when implementing materials or blur effects in iOS/Android UI."
---

# iOS Materials - 材质设计指南

基于 Apple Human Interface Guidelines 的材质设计规范。

## 核心概念

### 材质类型

- **Liquid Glass**: 动态材质，统一设计语言
- **Standard Materials**: 内容层内视觉区分

---

## Liquid Glass

### 特点

- 控制和导航元素的功能层
- 浮动在内容层上方
- 内容可透视和滚动
- 保持控件可读性

### 使用原则

- 不用于内容层
- 谨慎使用
- 仅用于重要功能元素

### 变体

- **Regular**: 模糊调整亮度，保持可读性
- **Clear**: 高度半透明，优先显示底层内容

### 颜色应用

- 谨慎使用颜色
- 保留给重要元素（状态指示、主操作）
- 背景着色优先于符号/文字着色

---

## 标准材质

### iOS/iPadOS

| 材质 | 描述 |
|------|------|
| ultraThin | 极薄 |
| thin | 薄 |
| regular | 标准（默认）|
| thick | 厚 |

### macOS

- 指定用途的标准材质
- 振动版本系统颜色
- 两种混合模式：behind window / within window

### tvOS

- Liquid Glass 用于导航元素
- 标准材质用于内容层

### visionOS

- Glass 材质（不可修改）
- 有限背景颜色范围
- 视觉深度振动效果

### watchOS

- 全屏模态视图材质
- 提供上下文和方向

---

## Android 适配

### 模糊效果

```xml
<!-- 背景模糊 -->
<androidx.blurkit.widget.BlurView
    android:id="@+id/blur_view"
    android:layout_width="match_parent"
    android:layout_height="match_parent">
    <!-- 内容 -->
</androidx.blurkit.widget.BlurView>
```

### 振动效果 (Vibrancy)

```kotlin
// 振动效果
val visualEffect = UIVisualEffectView(UIVibrancyEffect.blur)
```

### 磨砂背景

```xml
<!-- 使用 Material 组件 -->
<com.google.android.material.card.MaterialCardView
    android:layout_width="match_parent"
    android:layout_height="wrap_content"
    app:cardElevation="4dp"
    app:cardCornerRadius="12dp">
    <!-- 内容 -->
</com.google.android.material.card.MaterialCardView>
```

### Compose 模糊

```kotlin
// Jetpack Compose 修饰符
Modifier
    .graphicsLayer {
        alpha = 0.99f
    }
    .blur(radius = 20.dp)
```

### Surface 材质

```xml
<!-- Material 3 Surface -->
<Surface
    android:layout_width="match_parent"
    android:layout_height="wrap_content"
    tonalElevation="4dp">
    <!-- 内容 -->
</Surface>
```
