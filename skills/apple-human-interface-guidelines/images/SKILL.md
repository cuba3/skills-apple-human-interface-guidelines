---
name: "apple-human-interface-guidelines-images"
description: "iOS图片设计规范，包含分辨率、格式、图层图片。Invoke when preparing image assets for iOS/Android app."
---

# iOS Images - 图片设计指南

基于 Apple Human Interface Guidelines 的图片设计规范。

## 核心概念

### 像素与点

- Point: 抽象测量单位
- Scale Factor: 决定图像分辨率
- @1x, @2x, @3x 表示像素密度

### 平台分辨率

| 平台 | Scale Factors |
|------|---------------|
| iOS | @2x, @3x |
| iPadOS | @2x |
| watchOS | @2x |
| visionOS | @2x或更高 |
| macOS | @1x, @2x |
| tvOS | @1x, @2x |

---

## 图片格式

### 推荐格式

| 图片类型 | 推荐格式 |
|---------|---------|
| 位图/光栅 | PNG (无交错) |
| 8位色盘图标 | PNG |
| 照片 | JPEG/HEIC (优化) |
| 空间照片 | Stereo HEIC |
| 扁平图标/UI图标 | PDF/SVG |

### 格式说明

- **PNG**: 无损，适合图标和UI元素
- **JPEG**: 有损，适合照片
- **HEIC**: 高效，适合照片和空间内容
- **PDF/SVG**: 矢量，适合可缩放图标

---

## 最佳实践

### 色彩配置

- 包含颜色配置文件
- 确保跨设备颜色一致

### 测试

- 在实际设备上测试
- 检查缩放、拉伸、压缩问题

---

## tvOS 层级图片

### 视差效果

- 2-5层设计
- 焦点时抬起、摆动、表面发光
- 无焦点时变暗

### 设计要点

- 前景层：主角元素（角色、文字）
- 中间层：次要内容和阴影
- 背景层：不透明底色
- 保持简单和微妙

### 安全区域

- 焦点时边缘可能被裁切
- 重要内容保持在安全区域内

---

## visionOS 空间内容

### 图片显示

- 动态缩放匹配尺寸
- 像素与屏幕像素非1:1对应

### 空间照片

- 使用 Stereo HEIC 格式
- 添加空间元数据
- 使用羽毛玻璃背景效果

### 设计要点

- 使用矢量艺术
- 平衡质量和性能
- 避免在小尺寸使用位图

---

## Android 适配

### 密度资源

```
res/
  drawable-mdpi/    # @1x
  drawable-hdpi/    # @1.5x
  drawable-xhdpi/   # @2x
  drawable-xxhdpi/  # @3x
  drawable-xxxhdpi/ # @4x
```

### 矢量支持

```xml
<!-- 矢量图标 -->
<vector xmlns:android="http://schemas.android.com/apk/res/android"
    android:width="24dp"
    android:height="24dp"
    android:viewportWidth="24"
    android:viewportHeight="24">
    <!-- path data -->
</vector>
```

### WebP 格式

- 更小文件大小
- 支持透明度
- 适合照片和图标

### Launcher Icon

```xml
<!-- mipmap-anydpi-v26/ic_launcher.xml -->
<adaptive-icon>
    <background android:drawable="@color/ic_launcher_background"/>
    <foreground android:drawable="@drawable/ic_launcher_foreground"/>
</adaptive-icon>
```
