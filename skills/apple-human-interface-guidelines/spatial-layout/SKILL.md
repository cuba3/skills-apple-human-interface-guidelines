---
name: "apple-human-interface-guidelines-spatial-layout"
description: "visionOS空间布局设计规范，包含视野、深度、缩放。Invoke when designing spatial layout for visionOS app."
---

# iOS Spatial Layout - 空间布局设计指南

基于 Apple Human Interface Guidelines 的空间布局设计规范（主要针对 visionOS）。

## 核心概念

### 视野 (Field of View)

- 头部不动时可见的空间
- 因 Light Seal 配置和周边视力而异
- 重要内容保持在视野中心

### 不要锚定在头部

- 让用户自由环顾
- 避免让用户感到被困住

---

## 深度 (Depth)

### 视觉线索

- 距离、遮挡、阴影
- 系统自动应用效果

### 3D 内容

- 使用 RealityKit
- Volume 显示 3D 内容

### 设计要点

- 准确的深度线索避免不适
- 用深度展示层级
- 避免文字深度

---

## 缩放 (Scale)

### 动态缩放

- 内容无论距离保持可读可交互
- 窗口远离放大，靠近缩小

### 固定缩放

- 物体无论距离保持相同大小
- 适合展示物理产品

---

## Z轴层级

### 布局原则

- 近处物体更大、更吸引人
- 远处物体更小、不突出

### 内容排列

- 重要内容放靠近用户
- 考虑场景构成

---

## 窗口布局

### 窗口尺寸

- Small：快速交互（设置、通知）
- Medium：大多数应用功能
- Large：沉浸式丰富内容

### 标题栏

- 显示窗口标题和可选控件
- 提供上下文

---

## 定位

### 避免难以触及的区域

- 眼睛水平或以下最舒适
- 过高过低导致颈部疲劳

### 距离与交互

- 远距离物体不太可能被交互
- 近距离物体更可能被交互

### 元素间距

- 避免太近难以准确选择
- 足够的呼吸空间

---

## 悬停效果

### 视觉反馈

- 用户注视时显示
- 轻微但明显
- 不遮挡内容

### 一致性

- 整个应用保持一致
- 帮助用户建立预期

---

## 安全区域

- 重要内容远离窗口边缘
- 边缘交互困难
- 内容保持在中心

---

## Android 适配

注：空间布局主要针对 visionOS，Android 无直接对应。

### 3D 能力

- 使用 OpenGL ES 或 Vulkan
- ARCore 用于 AR 体验

### Z轴层级

- Android 使用 Elevation 实现深度
- Material Design 支持阴影

```xml
<!-- Elevation -->
<TextView
    android:layout_width="wrap_content"
    android:layout_height="wrap_content"
    android:elevation="4dp" />
```

### Compose 3D

```kotlin
// Jetpack Compose 3D 变换
Modifier.graphicsLayer {
    rotationX = 15f
    rotationY = 15f
    scaleX = 1f
    scaleY = 1f
}
```

### ARCore

```kotlin
// ARCore 应用
val session = ArCoreApk.getInstance().requestSession(this, ...)
```
