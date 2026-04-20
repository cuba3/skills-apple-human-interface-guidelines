---
name: "apple-human-interface-guidelines-writing"
description: "iOS写作规范，包含文案风格、大小写、常用术语。Invoke when writing UI text or copy for iOS/Android app."
---

# iOS Writing - 写作指南

基于 Apple Human Interface Guidelines 的界面写作规范。

## 核心原则

### 简洁

- 快速切入要点
- 使用短句和常用词
- 避免不必要的词（the, a, an, that）

### 友好语气

- 就像与用户对话
- 使用缩写
- 避免术语和技术缩写
- 界面中避免"please"（除错误消息外）

### 主动语态

- 更清晰直接
- 错误消息尤其重要

### 直接称呼

- 使用"你"和"你的"
- 更个人化

### 避免 condescension

- 避免 simply, just, obviously, merely
- 不要让人感到被催促或愚蠢

### 一致性

- 相同概念使用相同词
- 帮助用户建立心智模型

---

## 大小写规则

### 句式大小写 (Sentence Case)

用于大多数UI文本：
- 正文
- 标签
- Tab名称
- 按钮标签
- 菜单项
- 工具提示

### 标题大小写 (Title Case)

用于：
- 窗口标题
- 导航栏标题
- Table View Section Headers
- 一些大型字体处理
- 专有名词（包括应用名称）

### 按钮大小写

- 首字母大写，所有主要词大写
- 不大写介词（at, for, by, from, in, of, on, to, up, as）
- 除非是第一个或最后一个词

---

## 常见术语

### UI 元素

| 元素 | 术语 |
|------|------|
| Action sheet | Alert |
| Activity view | - |
| Alert | Alert |
| Button | 按钮 |
| Menu | 菜单 |
| Navigation bar | Navigation Bar |
| Search bar | Search Bar |
| Tab bar | Tab Bar |
| Table view | Table View |
| Text field | Text Field |
| Toolbar | Toolbar |
| Window | Window |

### 手势

| 手势 | 术语 |
|------|------|
| 点击 | Tap |
| 长按 | Touch and hold / Long press |
| 滑动 | Swipe, Swipe up/down/left/right |
| 滚动 | Scroll up/down/left/right |
| 拖动滑块 | Drag the slider |
| 缩放 | Pinch to zoom |
| 旋转 | Rotate |

---

## 错误消息

### 原则

- 解释发生了什么
- 说明如何解决
- 主动语态
- 避免责备

### 示例

| 不好的 | 好的 |
|--------|------|
| Invalid email address. | Enter an email address in the format: name@example.com. |

---

## 本地化注意

### 空间

- 某些语言需要多30%空间
- 避免长无间断字符串

### RTL

- 自动翻转
- 使用系统元素

### 文化

- 避免俚语
- 避免文化特定引用

---

## Android 适配

### 字符串资源

```xml
<!-- strings.xml -->
<string name="welcome">Welcome!</string>
<string name="enter_password">Enter your password</string>
<string name="delete_confirm">Delete this item?</string>
<string name="loading">Loading…</string>
<string name="error_generic">Something went wrong. Please try again.</string>
```

### 格式化字符串

```xml
<string name="welcome_user">Welcome, %1$s!</string>
<string name="item_count">%1$d items selected</string>
```

### 复数形式

```xml
<plurals name="item_count">
    <item quantity="one">%d item</item>
    <item quantity="other">%d items</item>
</plurals>
```

### 按钮文字

```xml
<!-- 使用动词 -->
<string name="action_done">Done</string>
<string name="action_cancel">Cancel</string>
<string name="action_delete">Delete</string>
<string name="action_edit">Edit</string>
<string name="action_save">Save</string>
```

### 避免

```xml
<!-- 避免 -->
<string name="error_occurred">An error has occurred.</string>

<!-- 使用 -->
<string name="error_generic">Something went wrong.</string>
```

### 大小写应用

```xml
<!-- 按钮：首字母大写 -->
<string name="btn_submit">Submit</string>
<string name="btn_cancel">Cancel</string>

<!-- 标签：句式大小写 -->
<string name="label_username">Username</string>
<string name="label_password">Password</string>

<!-- 标题：标题大小写 -->
<string name="title_settings">Settings</string>
<string name="title_profile">Profile</string>
```

### 占位符

```xml
<!-- 输入框提示 -->
<string name="hint_email">Email address</string>
<string name="hint_password">Password</string>
<string name="hint_search">Search</string>
```

### 辅助功能

```xml
<!-- ContentDescription 用于图片 -->
<ImageView
    android:src="@drawable/ic_menu"
    android:contentDescription="@string/menu" />

<!-- LabelFor 用于输入框 -->
<TextView
    android:id="@+id/label_email"
    android:text="@string/label_email"
    android:labelFor="@+id/input_email" />
```
