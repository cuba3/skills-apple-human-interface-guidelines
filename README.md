#项目包含三个主要部分：设计规范文档(docs)、Android资源示例(demo)、技能库(skills)。

## docs - Apple Human Interface Guidelines 设计文档

基于Apple HIG下载的设计规范原始文档，包含以下主题：

- accessibility.md：无障碍设计指南
- app-icons.md：应用图标设计
- branding.md：品牌设计原则
- color.md：色彩系统规范
- dark-mode.md：深色模式设计
- icons.md：图标设计规范
- images.md：图片资源指南
- immersive-experiences.md：visionOS沉浸式体验设计
- inclusion.md：包容性设计原则
- layout.md：布局系统规范
- materials.md：材质设计(Liquid Glass等)
- motion.md：动效设计原则
- privacy.md：隐私设计指南
- right-to-left.md：RTL布局设计
- sf-symbols.md：SF Symbols图标系统
- spatial-layout.md：visionOS空间布局
- typography.md：字体排版规范
- writing.md：界面文案撰写指南

## demo - Android 资源文件示例

### values/colors.xml

白天模式颜色配置，包含：

- 系统配色：sys_red、sys_blue、sys_green等12种iOS风格颜色
- 灰色系：sys_gray1至sys_gray6六个层级
- 黑白系：sys_black、sys_white
- VIP配色：vip_golden、vip_bg
- 渐变色：vip_gradient_peach、vip_gradient_purple、vip_gradient_blue、vip_gradient_gold
- 透明度颜色：sys_red_20、sys_blue_50、sys_black_25等

### values-night/colors.xml

夜间模式颜色配置，颜色值对应白天模式调整：

- 彩色系调整为更适合深色背景的亮色
- 黑白反向：sys_black变白、sys_white变黑
- 透明度调整适配深色模式

### values/dimens.xml

统一尺寸规范，基于8dp网格系统：

- 间距系统：space_0至space_8x，以8dp为基础倍数
- 圆角系统：radius_m(12dp)、radius_l(24dp)、radius_round_full(512dp)
- 字号系统：text_display_l(22sp)至text_caption(10sp)，映射iOS Dynamic Type
- iOS风格别名：largeTitle、title、headline、body、subhead、footnote、caption
- 布局高度：layout_height_xs(30dp)至layout_height_xxl(96dp)
- 图标尺寸：icon_xs_16(16dp)至icon_display_60(60dp)
- 头像尺寸：avatar_xs_24(24dp)至avatar_display_96(96dp)

## skills - Apple HIG 设计规范技能库

技能库将Apple HIG规范转换为可直接使用的Android开发资源，位于skills/apple-human-interface-guidelines 目录：

- accessibility：无障碍设计技能
- app-icons：应用图标技能
- branding：品牌设计技能
- colors：iOS系统配色方案技能，包含白天/夜间模式切换、透明度跨平台适配
- dark-mode：深色模式技能
- icons：图标设计技能
- images：图片资源技能
- immersive-experiences：沉浸式体验技能
- inclusion：包容性设计技能
- materials：材质设计技能(Liquid Glass)
- motion：动效设计技能
- privacy：隐私设计技能
- right-to-left：RTL布局技能
- sf-symbols：SF Symbols图标技能
- spatial-layout：空间布局技能
- typography-and-layout-dimens：字体排版和布局尺寸技能，整合Apple HIG Typography和Layout规范到Android dimens
- writing：界面文案技能

### 技能使用说明

每个技能目录包含SKILL.md文件，记录了：

- Apple HIG核心原则
- 平台规范参考(iOS、iPadOS、tvOS、visionOS、watchOS、macOS)
- Android实现示例
- 使用场景指南

### 核心技能说明

#### colors技能

提供iOS系统颜色到Android的完整映射：

- 12种iOS系统色：red、orange、yellow、green、mint、teal、cyan、blue、indigo、purple、pink、brown
- 6级灰色：sys_gray1至sys_gray6
- VIP配色：vip_golden、vip_bg
- 跨平台透明度支持：Android(ARGB)、iOS/CSS(RGBA)、Flutter

#### typography-and-layout-dimens技能

整合字体排版和布局尺寸规范：

- 字体大小映射iOS Dynamic Type
- 间距系统基于8dp网格
- iOS风格别名便于对照设计稿
- 包含Android TextAppearance样式定义

## 使用建议

1. 新开发优先使用demo/values/dimens.xml中的标准化键名
2. 颜色使用demo/values/colors.xml中的语义化命名
3. 查阅skills技能库了解设计原则和实现细节
4. 深色模式自动切换由values-night目录处理
