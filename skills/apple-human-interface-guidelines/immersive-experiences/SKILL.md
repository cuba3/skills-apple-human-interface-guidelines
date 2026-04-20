---
name: "apple-human-interface-guidelines-immersive-experiences"
description: "visionOS沉浸式体验设计规范，包含空间、穿透、全景内容。Invoke when designing spatial/immersive experiences for visionOS."
---

# iOS Immersive Experiences - 沉浸式体验设计指南

基于 Apple Human Interface Guidelines 的沉浸式体验设计规范（主要针对 visionOS）。

## 核心概念

### 空间类型

- **Shared Space**: 与其他应用并列运行
- **Full Space**: 独占空间，隐藏其他应用

### 穿透 (Passthrough)

- 实时视频显示现实环境
- 数字旋钮管理穿透程度
- 靠近物体时自动变暗

---

## 沉浸风格

### Mixed (混合)

- 与穿透混合
- 不定义边界
- 靠近物体时内容半透明

### Progressive (渐进)

- 自定义环境部分替代穿透
- 可定义沉浸范围（120-360度）
- 数字旋钮调整深度

### Full (完全)

- 360度全沉浸
- 完全替代穿透
- 传输到新环境

---

## 最佳实践

### _launch 策略

- 优先使用 Shared Space 或 Mixed
- 让用户选择何时加深沉浸

### 沉浸时刻

- 仅为有意义的内容和时刻
- 不需要完全沉浸的不要强制
- 使用提示引导注意力

### 视觉舒适

- 重要内容放在视野中心
- 避免边缘快速运动
- 避免让用户旋转虚拟世界

### 过渡设计

- 平滑可预测
- 让用户选择进出时机
- 明确退出按钮含义

---

## 虚拟手

### 设计要点

- 匹配用户手的位置和手势
- 避免过大的虚拟手
- 数据中断时淡出

---

## 环境创建

### 设计原则

- 最小化干扰内容
- 帮助区分可交互对象
- 动画保持微妙
- 创建广阔环境
- 使用空间音频

### 避免

- 扁平360度图像
- 缺乏地面平面
- 资产重复

---

## Android 适配

注：沉浸式体验主要针对 visionOS，Android 无直接对应。

### 相关概念

- **全面屏沉浸模式**: 隐藏状态栏和导航栏
- **ARCore**: 增强现实体验

### 沉浸模式实现

```kotlin
// 隐藏系统UI
window.decorView.systemUiVisibility = (
    View.SYSTEM_UI_FLAG_IMMERSIVE_STICKY
    or View.SYSTEM_UI_FLAG_FULLSCREEN
    or View.SYSTEM_UI_FLAG_HIDE_NAVIGATION
)
```

### AR 应用

```kotlin
// ARCore 会话配置
val config = Config(session)
config.updateMode = Config.UpdateMode.LATEST_CAMERA_IMAGE
session.configure(config)
```
