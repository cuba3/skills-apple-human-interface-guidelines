# Apple Human Interface Guidelines for Android

将 Apple 设计规范转换为 Android 可直接使用的资源库。

## ✨ 特性

- 📐 **完整的设计规范** - 基于 Apple HIG 的 Android 实现
- 🎨 **开箱即用的颜色** - iOS 系统色 + 语义化命名
- 📏 **标准化尺寸** - 8dp 网格系统 + iOS Dynamic Type 映射
- 🌙 **深色模式支持** - values-night 自动切换
- 🤖 **AI 技能库** - 可集成到 AI 编程助手的技能系统

## 📁 项目结构

```
skills-apple-human-interface-guidelines/
├── docs/           # Apple HIG 原始设计文档
├── demo/           # Android 资源文件示例
│   ├── values/    # 白天模式 (colors.xml, dimens.xml)
│   └── values-night/  # 夜间模式
└── skills/         # AI 技能库
    └── apple-human-interface-guidelines/
        ├── colors/
        ├── typography-and-layout-dimens/
        └── ... (其他技能)
```

## 🚀 快速开始

### 1. 克隆仓库

```bash
git clone https://github.com/cuba3/skills-apple-human-interface-guidelines.git
cd skills-apple-human-interface-guidelines
```

### 2. 选择使用方式

#### 方式一：使用 Android 资源文件

将 `demo` 目录下的资源文件复制到你的 Android 项目：

```
你的Android项目/
└── app/src/main/res/
    ├── values/
    │   ├── colors.xml      # 复制到这里
    │   └── dimens.xml       # 复制到这里
    └── values-night/
        └── colors.xml      # 深色模式
```

#### 方式二：集成 AI 技能库

如果你使用的是支持技能系统的 AI 编程助手，可以将技能库复制到对应目录：

```bash
cp -r skills/apple-human-interface-guidelines {你的项目路径}/skills/
```

> 💡 具体路径取决于你的 AI 助手技能库配置，请查阅对应工具的文档。

## 📦 资源说明

### 颜色 (colors.xml)

| 类型 | 示例 | 说明 |
|------|------|------|
| iOS 系统色 | `sys_red`, `sys_blue`, `sys_green` | 12 种 iOS 风格颜色 |
| 灰色系 | `sys_gray1` ~ `sys_gray6` | 6 级灰度 |
| VIP 配色 | `vip_golden`, `vip_bg` | 金色主题 |
| 透明度 | `sys_red_20` (32% 透明) | 跨平台透明色 |

### 尺寸 (dimens.xml)

| 类型 | 示例 | 说明 |
|------|------|------|
| 间距 | `space_4`, `space_8`, `space_16` | 8dp 网格 |
| 字号 | `text_title`, `text_body`, `text_caption` | iOS Dynamic Type |
| 圆角 | `radius_m` (12dp), `radius_l` (24dp) | 统一圆角 |
| 图标 | `icon_24`, `icon_32`, `icon_48` | 标准图标尺寸 |

## 📖 技能库

每个技能目录包含 `SKILL.md`，记录了：

- 🎯 Apple HIG 核心原则
- 📱 平台规范参考
- 🤖 Android 实现示例
- 💡 使用场景指南

可用技能：

- `accessibility` - 无障碍设计
- `app-icons` - 应用图标
- `branding` - 品牌设计
- `colors` - 色彩系统
- `dark-mode` - 深色模式
- `icons` - 图标设计
- `images` - 图片资源
- `materials` - 材质设计 (Liquid Glass)
- `motion` - 动效设计
- `typography-and-layout-dimens` - 字体与布局
- `writing` - 界面文案
- ... 更多

## 📄 许可证

基于 Apple Human Interface Guidelines。
