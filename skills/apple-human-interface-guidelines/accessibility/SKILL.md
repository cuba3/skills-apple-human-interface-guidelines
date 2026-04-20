---
name: "apple-human-interface-guidelines-accessibility"
description: "iOS无障碍设计指南，包含VoiceOver、动态字体、色彩对比度等。Invoke when implementing accessibility features in Android or iOS app."
---

# iOS Accessibility - 无障碍设计指南

基于 Apple Human Interface Guidelines 的无障碍设计规范，帮助创建包容性体验。

## 核心原则

无障碍界面具备以下特点：
- **直观性 (Intuitive)**: 使用熟悉一致的交互方式
- **可感知 (Perceivable)**: 不依赖单一感官传达信息
- **可适配 (Adaptable)**: 支持系统无障碍功能和个人设置

---

## 视觉 (Vision)

### 动态类型 (Dynamic Type)

支持用户调整字体大小，建议提供至少200%的放大倍数。

| 平台 | 默认字号 | 最小字号 |
|------|----------|----------|
| iOS, iPadOS | 17pt | 11pt |
| macOS | 13pt | 10pt |
| tvOS | 29pt | 23pt |
| visionOS | 17pt | 12pt |
| watchOS | 16pt | 12pt |

### 字体粗细建议

- 细字重 (Thin/Light) 需要更大字号提高可读性
- 粗字重更适合小字号文本
- 避免在可读性要求高的场景使用细字重

### 色彩对比度

遵循 WCAG 2.1 Level AA 标准：

| 字重 | 最小对比度 |
|------|------------|
| ≤17pt | 4.5:1 |
| ≥18pt | 3:1 |
| 粗体 (任何字号) | 3:1 |

### 色彩使用建议

- 使用系统定义颜色，自动适配无障碍设置
- 不仅依赖颜色传达信息，添加形状或图标辅助
- 支持 Increase Contrast 设置

### VoiceOver 支持

- 为所有交互元素提供 accessibility label
- 使用语义化标记描述界面结构
- 确保操作顺序符合逻辑

---

## 听觉 (Hearing)

### 媒体内容无障碍

| 方式 | 适用场景 |
|------|----------|
| 字幕 (Captions) | 视频/音频内容同步文字 |
| 字幕 (Subtitles) | 对话翻译 |
| 音频描述 (Audio Descriptions) | 视频中视觉信息解说 |
| 文字稿 (Transcripts) | 播客、有声书 |

### 声音与触觉结合

- 音频提示配合触觉反馈
- 游戏和空间应用中补充视觉提示
- 重要信息不单独通过音频传达

---

## 运动 (Mobility)

### 触控区域尺寸

| 平台 | 默认触控尺寸 | 最小触控尺寸 |
|------|-------------|--------------|
| iOS, iPadOS | 44x44pt | 28x28pt |
| macOS | 28x28pt | 20x20pt |
| tvOS | 66x66pt | 56x56pt |
| visionOS | 60x60pt | 28x28pt |
| watchOS | 44x44pt | 28x28pt |

### 元素间距

- 有边框元素：周围至少12pt内边距
- 无边框元素：周围至少24pt内边距

### 手势设计

- 优先使用简单手势
- 提供手势替代方案（如按钮）
- 避免复杂的多指多手手势

### 语音控制

- 支持 Voice Control 语音指令
- 正确标注界面元素
- 集成 Siri 和 Shortcuts

---

## 认知 (Cognitive)

### 简化交互

- 使用系统熟悉的手势和行为
- 减少时间限制的界面元素
- 提供明确的操作反馈

### 游戏难度选项

- 提供可自定义的难度设置
- 考虑不同认知能力需求

### 动画处理

- 支持 Reduce Motion 设置
- 减少自动重复动画
- 避免快速闪烁

### Assistive Access

为认知障碍用户优化：
- 识别核心功能，移除非关键元素
- 单屏单一交互
- 危险操作双重确认

---

## visionOS 特殊考虑

### 优先考虑舒适度

- 内容保持在视野范围内
- 减少周边视觉的运动
- 避免大幅快速移动
- 避免内容固定在头部位置
- 减少重复大幅手势

### 支持 Pointer Control

- 支持头部和手部指针控制
- 支持 Zoom 放大功能

---

## Android 适配要点

### 字号系统

```xml
<!-- 基础字号系统 -->
<dimen name="text_display_l">22sp</dimen>
<dimen name="text_title_l">20sp</dimen>
<dimen name="text_title_m">18sp</dimen>
<dimen name="text_body_l">17sp</dimen>
<dimen name="text_body_m">16sp</dimen>
<dimen name="text_body_s">14sp</dimen>
<dimen name="text_note_m">12sp</dimen>
<dimen name="text_caption">10sp</dimen>
```

### 对比度检查

- 前景与背景对比度至少 4.5:1
- 大文本至少 3:1
- 使用工具验证：WebAIM Contrast Checker

### 触控区域

- 最小触控目标 48x48dp (约44pt)
- 重要元素使用更大触控区域

### 内容描述

```xml
<!-- ContentDescription for images -->
<ImageView
    android:src="@drawable/ic_menu"
    android:contentDescription="@string/menu_description" />

<!-- Semantics for Compose -->
Modifier.semantics {
    contentDescription = "Add to favorites"
}
```

### 字体缩放支持

```xml
<!-- 支持 sp 单位自动缩放 -->
<TextView
    android:textSize="16sp"
    android:textColor="?android:attr/textColorPrimary" />
```

### 无障碍服务兼容

- 测试 TalkBack 朗读顺序
- 确保焦点顺序合理
- 提供明确的焦点指示器
