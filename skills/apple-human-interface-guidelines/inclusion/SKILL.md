---
name: "apple-human-interface-guidelines-inclusion"
description: "iOS包容性设计指南，包含语言、文化、多样性。Invoke when designing inclusive app experience."
---

# iOS Inclusion - 包容性设计指南

基于 Apple Human Interface Guidelines 的包容性设计规范。

## 核心概念

### 包容性设计原则

- 简单、直观的体验是核心
- 同理心是重要工具
- 考虑多元视角

### 多元身份特征

- 年龄
- 性别和性别认同
- 种族和民族
- 性取向
- 身体属性
- 认知能力
- 永久性、暂时性和情境性残疾
- 语言和文化
- 宗教
- 教育
- 政治或哲学观点
- 社会和经济背景

---

## 语言包容性

### 语气与用词

- 使用平实、易懂的语言
- 直接称呼"你"和"你的"
- 避免技术术语，或使用时定义
- 用直白的表达替代俚语
- 谨慎使用幽默

### 性别中立

- 避免不必要的性别指代
- 使用中性名词
- 提供包容性选项（非binary、自我认同、拒绝回答）

### 避免偏见

- 避免刻板印象
- 呈现多样性
- 避免文化特定引用

---

## 无障碍

### 残疾是光谱

- 各种视觉、听觉、运动、认知能力
- 每个人都会经历暂时性或情境性残疾

### 设计要点

- 包含残疾人
- 使用人为本的语言
- 优先简单性和可感知性

---

## 人士呈现

### 多样性

- 呈现各种种族背景、体型、年龄、能力
- 避免刻板印象
- 展现熟悉、可 relatable 的环境和物品

---

## 本地化准备

### 国际化

- 准备好处理其他语言和地区
- 使用 SF Symbols（支持语言特定符号）
- 注意颜色文化含义

---

## Android 适配

### 字符串资源

```xml
<!-- strings.xml -->
<string name="welcome_message">Welcome!</string>

<!-- 避免 -->
<string name="welcome_message">Welcome, user!</string>
```

### 性别中立

```xml
<!-- 包容性表达 -->
<string name="subscriber_posts">Subscribers can post recipes to your shared folder.</string>

<!-- 避免 -->
<string name="subscriber_posts">A subscriber can post his or her recipes to your shared folder.</string>
```

### RTL 支持

```xml
<!-- 自动镜像 -->
<TextView
    android:layout_width="match_parent"
    android:layout_height="wrap_content"
    android:text="@string/hello" />
```
