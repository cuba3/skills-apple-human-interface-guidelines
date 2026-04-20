---
name: "apple-human-interface-guidelines-colors"
description: "iOS系统配色方案，包含Apple HIG颜色和VIP配色，支持白天/夜间模式切换。Invoke when user needs iOS-style colors for Android app."
---

# iOS System Colors

基于 Apple Human Interface Guidelines 的系统配色方案，包含白天和夜间模式。

## 白天模式 (Light Mode)

### 彩色系

| 颜色名称 | Hex值 |
|----------|-------|
| sys_red | #FF3B30 |
| sys_orange | #FF9500 |
| sys_yellow | #FFCC00 |
| sys_green | #34C759 |
| sys_mint | #00c7be |
| sys_teal | #30b0c7 |
| sys_cyan | #32ade6 |
| sys_blue | #007AFF |
| sys_indigo | #5856D6 |
| sys_purple | #AF52DE |
| sys_pink | #FF2D55 |
| sys_brown | #a2845e |

### VIP配色 (opn48 design)

| 颜色名称 | Hex值 |
|----------|-------|
| vip_golden | #6F2C02 |
| vip_bg | #FFBE6B |

### 灰色系

| 颜色名称 | Hex值 |
|----------|-------|
| sys_gray1 | #8E8E93 |
| sys_gray2 | #AEAEB2 |
| sys_gray3 | #C7C7CC |
| sys_gray4 | #D1D1D6 |
| sys_gray5 | #E5E5EA |
| sys_gray6 | #F2F2F7 |

### 黑白系

| 颜色名称 | Hex值 |
|----------|-------|
| sys_black | #000000 |
| sys_white | #FFFFFF |

---

## 夜间模式 (Dark Mode)

### 彩色系

| 颜色名称 | Hex值 |
|----------|-------|
| sys_red | #FF453A |
| sys_orange | #FF9F0A |
| sys_yellow | #FFD60A |
| sys_green | #30D158 |
| sys_mint | #66D4CF |
| sys_teal | #40C8E0 |
| sys_cyan | #64D2FF |
| sys_blue | #0A84FF |
| sys_indigo | #5E5CE6 |
| sys_purple | #BF5AF2 |
| sys_pink | #FF375F |
| sys_brown | #AC8E68 |

### VIP配色 (opn48 design)

| 颜色名称 | Hex值 |
|----------|-------|
| vip_golden | #FFBE6B |
| vip_bg | #6F2C02 |

### 灰色系

| 颜色名称 | Hex值 |
|----------|-------|
| sys_gray1 | #8E8E93 |
| sys_gray2 | #636366 |
| sys_gray3 | #48484A |
| sys_gray4 | #3A3A3C |
| sys_gray5 | #2C2C2E |
| sys_gray6 | #1C1C1E |

### 黑白系 (反向)

| 颜色名称 | Hex值 |
|----------|-------|
| sys_black | #FFFFFF |
| sys_white | #000000 |

---

## 使用方式

### Android (values/colors.xml)

```xml
<?xml version="1.0" encoding="utf-8"?>
<resources>
    <!-- 白天模式颜色 (默认) -->
    <color name="sys_red">#FF3B30</color>
    <color name="sys_blue">#007AFF</color>
    <!-- ... 其他颜色 -->
</resources>
```

### Android 夜间模式 (values-night/colors.xml)

```xml
<?xml version="1.0" encoding="utf-8"?>
<resources>
    <!-- 夜间模式颜色 -->
    <color name="sys_red">#FF453A</color>
    <color name="sys_blue">#0A84FF</color>
    <!-- ... 其他颜色 -->
</resources>
```

---

## 使用场景

1. **UI组件着色**: Button、Icon、Badge等使用sys_blue等品牌色
2. **状态指示**: 成功(green)、警告(yellow)、错误(red)
3. **文字颜色**: 标题(sys_black/white)、次要文字(sys_gray1/2)
4. **背景色**: 卡片(sys_gray6)、分割线(sys_gray5)
5. **VIP特权**: vip_golden用于VIP标识，vip_bg用于VIP专区背景

---

## 透明度颜色

基于已有配色，在16进制RGB前增加两位十六进制数表示透明度。

### 跨平台透明度格式差异

| 平台 | 格式 | 透明度位置 | 示例 |
|------|------|-----------|------|
| Android (ColorInt) | ARGB | 前两位 | #AA007AFE |
| iOS (UIColor) | RGBA | 后两位 | #007AFEAA |
| CSS / Web | RGBA | 后两位 | #007AFEAA |
| Flutter | 根据传入方式 | - | Color(0xAA007AFE) |

### 格式说明

- **透明度通用规则**: 00 = 完全透明，FF = 完全不透明
- **Android (ARGB)**: 透明度在前，RGB在后
- **iOS / CSS / Web (RGBA)**: RGB在前，透明度在后

### 透明度对照表

| 透明度 | 十六进制值 |
|--------|------------|
| 0% (完全透明) | 00 |
| 5% | 0D |
| 10% | 1A |
| 20% | 33 |
| 30% | 4D |
| 40% | 66 |
| 50% | 80 |
| 60% | 99 |
| 70% | B3 |
| 80% | CC |
| 90% | E6 |
| 100% (完全不透明) | FF |

### 跨平台转换示例

以 50% 透明度 的 #007AFF (蓝色) 为例：

| 平台 | 格式 | 颜色值 |
|------|------|--------|
| Android (XML) | ARGB | #80007AFF |
| Android (Kotlin Color Int) | ARGB | 0x80007AFF |
| iOS (Swift) | RGBA | Color(red: 0.0, green: 0.478, blue: 1.0, opacity: 0.5) 或 #007AFF80 |
| CSS / Web | RGBA | rgba(0, 122, 255, 0.5) 或 #007AFF80 |
| Flutter | 根据使用 | Color(0x80007AFF) |

### 命名规则

格式: `{原色名}_{透明度百分比}`

例如: `sys_red_20` 表示20%透明度的sys_red

### 白天模式示例

| 颜色名称 | Hex值 | 描述 |
|----------|-------|------|
| sys_red_20 | #33FF3B30 | 20%透明度红色 |
| sys_red_50 | #80FF3B30 | 50%透明度红色 |
| sys_blue_20 | #33007AFF | 20%透明度蓝色 |
| sys_gray3_30 | #4DC7C7CC | 30%透明度灰色 |

### 夜间模式示例

| 颜色名称 | Hex值 | 描述 |
|----------|-------|------|
| sys_red_20 | #33FF453A | 20%透明度红色 |
| sys_red_50 | #80FF453A | 50%透明度红色 |
| sys_blue_20 | #330A84FF | 20%透明度蓝色 |
| sys_gray3_30 | #4D48484A | 30%透明度灰色 |

### Android使用示例

```xml
<!-- values/colors.xml (白天) -->
<color name="sys_red_20">#33FF3B30</color>
<color name="sys_blue_50">#80007AFF</color>

<!-- values-night/colors.xml (夜晚) -->
<color name="sys_red_20">#33FF453A</color>
<color name="sys_blue_50">#800A84FF</color>
```

### CSS / Web 使用示例

```css
/* CSS 变量方式 (推荐) */
:root {
    --sys-red: #FF3B30;
    --sys-red-50: rgba(255, 59, 48, 0.5);
    --sys-blue: #007AFF;
    --sys-blue-50: rgba(0, 122, 255, 0.5);
}

/* 直接使用 */
.button-overlay {
    background-color: rgba(255, 59, 48, 0.2);
}

/* 使用8位十六进制 (iOS/CSS兼容) */
.card-overlay {
    background-color: #FF3B3033; /* 20% 透明度 */
}
```

### Flutter 使用示例

```dart
// 使用ARGB格式 (与Android一致)
Color sysRed20 = Color(0x33FF3B30);
Color sysBlue50 = Color(0x80007AFF);

// 使用RGBA参数
Color sysBlue50Alt = Color.fromARGB(128, 0, 122, 255);
```

### 使用场景

1. **遮罩层**: 半透明黑色/白色覆盖层
2. **图标填充**: 图标使用半透明颜色作为填充
3. **背景装饰**: 卡片弱化背景色
4. **边框/分割线**: 使用低透明度颜色作为细微分割

### 注意事项

1. **Android XML**: 透明度放在RGB前面 (ARGB)
2. **iOS / CSS**: 透明度放在RGB后面 (RGBA)
3. **Flutter**: Color() 构造函数使用 ARGB 格式 (0xAARRGGBB)
4. **Web 开发**: 推荐使用 `rgba()` 或 `hsla()` 函数，兼容性好
5. **设计工具**: Sketch/Figma 导出通常是 RGBA 格式，Android 使用需转换
