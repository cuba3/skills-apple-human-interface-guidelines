---
name: "apple-human-interface-guidelines-motion"
description: "iOS动画设计规范，包含反馈动画、平台能力、visionOS运动。Invoke when implementing animations in iOS/Android app."
---

# iOS Motion - 动画设计指南

基于 Apple Human Interface Guidelines 的动画设计规范。

## 核心原则

### 有目的的动画

- 支持而非掩盖体验
- 不要为动画而动画
- 过度动画让人分心或不适应

### 动画可选

- 不是传达重要信息的唯一方式
- 配合触觉和音频反馈

---

## 反馈动画

### 现实感

- 遵循用户手势和预期
- 不合理的动画让人迷惑

### 简洁精确

- 短暂精确的动画更轻量
- 与成功动作精确绑定

### 可取消

- 不要让人等待动画完成
- 让人能立即做其他事

---

## 平台能力

### 游戏动画

- 保持 30-60 fps
- 默认设置让用户可直接享受

### 用户自定义

- 提供画质/性能选项
- 电量优化选项

---

## visionOS 特殊考虑

### 舒适度优先

- 避免边缘运动
- 避免大幅运动
- 让人避免不适

### 大物体移动

- 增加透明度
- 降低对比度

### 物体移动

- 需要时使用淡入淡出
- 避免旋转虚拟世界

### 震动

- 避免持续震动（约0.2Hz敏感）
- 低幅度，透明内容

---

## Android 适配

### 属性动画

```kotlin
// 淡入动画
ObjectAnimator.ofFloat(view, View.ALPHA, 0f, 1f).apply {
    duration = 300
    start()
}

// 缩放动画
view.animate()
    .scaleX(1.2f)
    .scaleY(1.2f)
    .setDuration(150)
    .withEndAction { 
        view.animate()
            .scaleX(1f)
            .scaleY(1f)
            .start()
    }
    .start()
```

### 动画资源

```xml
<!-- res/anim/fade_in.xml -->
<alpha xmlns:android="http://schemas.android.com/apk/res/android"
    android:duration="300"
    android:fromAlpha="0.0"
    android:toAlpha="1.0"
    android:interpolator="@android:anim/accelerate_decelerate_interpolator" />
```

### MotionLayout

```xml
<MotionScene xmlns:android="http://schemas.android.com/apk/res/android">
    <Transition
        motion:constraintSetStart="@id/start"
        motion:constraintSetEnd="@id/end"
        motion:duration="300">
        <KeyFrameSet>
            <KeyAttribute
                motion:motionTarget="@id/button"
                motion:framePosition="50"
                android:scaleX="1.1"
                android:scaleY="1.1" />
        </KeyFrameSet>
    </Transition>
</MotionScene>
```

### Compose 动画

```kotlin
// AnimatedVisibility
AnimatedVisibility(
    visible = isVisible,
    enter = fadeIn() + expandVertically(),
    exit = fadeOut() + shrinkVertically()
) {
    Text("Content")
}

// animateContentSize
Column(modifier = Modifier.animateContentSize()) {
    // 内容
}
```

### 触觉反馈

```kotlin
// 触觉反馈
val vibrator = getSystemService(Context.VIBRATOR_SERVICE) as Vibrator
if (Build.VERSION.SDK_INT >= Build.VERSION_CODES.O) {
    vibrator.vibrate(VibrationEffect.createOneShot(50, VibrationEffect.DEFAULT_AMPLITUDE))
}
```

### 减少动画 (Reduce Motion)

```kotlin
// 检测减少动画设置
val reduceMotionEnabled = Settings.Secure.getInt(
    contentResolver,
    Settings.Secure.ACCESSIBILITY_DISPLAY_REDUCED_MOTION_ENABLED,
    0
) == 1
```

### 动画插值器

| 类型 | 用途 |
|------|------|
| accelerate_decelerate | 平滑加速减速 |
| accelerate | 加速进入 |
| decelerate | 减速退出 |
| bounce | 弹跳效果 |
| overshoot | 超越并回弹 |
