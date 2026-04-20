---
name: "apple-human-interface-guidelines-app-icons"
description: "iOS应用图标设计规范，包含分层设计、尺寸规格、平台差异。Invoke when designing app icons for iOS/Android or creating icon assets."
---

# iOS App Icons - 应用图标设计指南

基于 Apple Human Interface Guidelines 的应用图标设计规范。

## 设计原则

### 核心要求

- 简洁明了：简单图标更易识别和记忆
- 视觉一致：跨平台保持一致设计
- 聚焦核心：选择能捕捉应用本质的元素
- 避免内容：除非必要，否则不包含文字

---

## 分层设计 (Layer Design)

### iOS/iPadOS/macOS/watchOS

- 背景层 + 一个或多个前景层
- 系统应用 Liquid Glass 效果（高光、磨砂、半透明）
- 响应光线变化和设备运动

### tvOS

- 2-5层设计创造动态感
- 焦点效果：抬起、前后摆动、表面发光
- 视差效果创造深度感

### visionOS

- 背景层 + 1-2个前景层
- 3D效果，视角变化时展开
- 阴影和浮雕效果

---

## 平台规格

### 布局与尺寸

| 平台 | 布局形状 | 图标形状 | 布局尺寸 | 风格 |
|------|---------|---------|---------|------|
| iOS, iPadOS, macOS | 正方形 | 圆角矩形 | 1024x1024px | 分层 |
| tvOS | 横向矩形 | 圆角矩形 | 800x480px | 分层(视差) |
| visionOS | 正方形 | 圆形 | 1024x1024px | 分层(3D) |
| watchOS | 正方形 | 圆形 | 1088x1088px | 分层 |

### 变体支持

- Default (默认)
- Dark (暗色)
- Clear Light (透明亮)
- Clear Dark (透明暗)
- Tinted Light (着色亮)
- Tinted Dark (着色暗)

---

## 设计要点

### 保持简洁

- 简单形状易于识别
- 避免细小视觉特征
- 使用纯色或渐变背景

### 避免的内容

- Apple硬件产品复制
- UI组件复制
- 照片（细节在缩放时丢失）
- 应用截图

### 前景层设计

- 清晰边缘（避免柔化边缘）
- 透明度变化增加深度感
- 使用矢量图形

---

## Android 适配

### 图标生成

```xml
<!-- mipmap-anydpi-v26/ic_launcher.xml -->
<adaptive-icon xmlns:android="http://schemas.android.com/apk/res/android">
    <background android:drawable="@drawable/ic_launcher_background"/>
    <foreground android:drawable="@drawable/ic_launcher_foreground"/>
</adaptive-icon>
```

### 尺寸规格

| 密度 | 尺寸 |
|------|------|
| mdpi | 48x48 |
| hdpi | 72x72 |
| xhdpi | 96x96 |
| xxhdpi | 144x144 |
| xxxhdpi | 192x192 |

### 形状遮罩

- Android 自动应用圆角遮罩
- 需提供方形资源
- legacy图标使用圆角矩形

---

## 设计模板

### 安全区域

- 重要内容居中
- 避免边缘裁切
- 参考 Apple Design Resources 模板

### 图层导出

- iOS: 使用 Icon Composer
- tvOS/visionOS: Xcode 图像堆栈
