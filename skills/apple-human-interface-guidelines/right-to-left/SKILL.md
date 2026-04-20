---
name: "apple-human-interface-guidelines-right-to-left"
description: "iOS RTL布局设计规范，包含文字对齐、图标翻转、本地化。Invoke when implementing RTL layout or localizing for Arabic/Hebrew."
---

# iOS Right to Left - RTL 布局设计指南

基于 Apple Human Interface Guidelines 的从右到左 (RTL) 布局设计规范。

## 核心概念

### 系统支持

- iOS UI框架默认支持 RTL
- 系统组件自动翻转
- 使用系统元素通常无需修改

---

## 文字对齐

### 基本对齐

- LTR：左对齐
- RTL：右对齐
- 与界面方向匹配

### 段落对齐

- 1-2行：匹配阅读方向
- 3行以上：匹配语言本身
- 避免难读

### 列表对齐

- 所有项目统一对齐
- 包括使用不同脚本的项目

---

## 数字与字符

### 数字系统

- 希伯来语：西方阿拉伯数字
- 阿拉伯语：西方或东方阿拉伯数字

### 数字顺序

- 特定数字顺序不变（电话号码、信用卡号）
- 显示进度的数字需要翻转

---

## 控件翻转

### 需要翻转

- 滑块和进度指示器
- 导航控件（前进/后退）
- 文字对齐的图标

### 保持方向

- 实际方向（"向右"按钮始终指向右）
- 指向屏幕区域的控件

---

## 图片处理

### 翻转图片

- 避免翻转照片、插图、艺术作品
- 有意义顺序的图片需要翻转位置

---

## 图标处理

### SF Symbols

- 自动提供 RTL 变体
- 本地化符号

### 需要翻转

- 表示文字或阅读方向
- 表示前进/后退运动

### 不翻转

- 标志/通用符号
- 表示真实世界对象的图标
- 时钟等

---

## Android 适配

### 布局方向

```xml
<!-- 自动支持 RTL -->
<TextView
    android:layout_width="match_parent"
    android:layout_height="wrap_content"
    android:text="@string/hello" />
```

### Start/End 属性

```xml
<!-- 使用 start/end 替代 left/right -->
<LinearLayout
    android:layout_width="match_parent"
    android:layout_height="wrap_content"
    android:orientation="horizontal">

    <TextView
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_marginStart="8dp" />

    <TextView
        android:layout_width="0dp"
        android:layout_height="wrap_content"
        android:layout_weight="1"
        android:gravity="start" />
</LinearLayout>
```

### RTL 布局

```xml
<!-- 支持 RTL -->
android:gravity="start"
android:paddingStart="16dp"
android:paddingEnd="16dp"
android:layout_marginStart="8dp"
android:layout_marginEnd="8dp"
```

### Drawable 翻转

```xml
<!-- 翻转图标 -->
<ImageView
    android:src="@drawable/ic_arrow"
    android:layoutDirection="rtl" />

<!-- 或使用 -->
<ImageView
    app:srcCompat="@drawable/ic_arrow"
    android:layoutDirection="locale" />
```

### 检测 RTL

```kotlin
val isRtl = layoutDirection == View.LAYOUT_DIRECTION_RTL

// 或
val isRtl = resources.configuration.layoutDirection == 
    Configuration.SCREEN_LAYOUT_DIRECTION_RTL
```

### 本地化资源

```
res/
  values/strings.xml        # 默认（英语）
  values-ar/strings.xml    # 阿拉伯语
  values-he/strings.xml    # 希伯来语
```

### 数字格式

```kotlin
// 使用本地化数字格式
NumberFormat.getInstance(Locale.getDefault()).format(1234567)
```
