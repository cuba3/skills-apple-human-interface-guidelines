---
name: "apple-human-interface-guidelines-privacy"
description: "iOS隐私设计指南，包含权限请求、用户数据处理。Invoke when implementing privacy features or permission requests in iOS/Android app."
---

# iOS Privacy - 隐私设计指南

基于 Apple Human Interface Guidelines 的隐私设计规范。

## 核心原则

### 数据收集

- 只请求实际需要的数据
- 过多数据让用户不信任
- 给用户对数据的精确控制

### 透明度

- 清晰说明如何收集和使用数据
- 尊重用户选择（Hide My Email等）

### 本地处理

- 尽可能在设备上处理数据
- 避免不必要的服务器往返

---

## 权限请求

### 需要权限的内容

- 个人数据：位置、健康、财务、联系人
- 用户生成内容：消息、日历、联系人
- 受保护资源：相机、麦克风、蓝牙、Wi-Fi
- 设备功能
- 广告标识符

### 请求时机

- 明确需要时再请求
- 理想：用户尝试使用需要权限的功能时
- 避免启动时请求（除非必需）

### 说明文字

- 清晰描述如何使用
- 简洁、具体、易懂
- 使用主动语态
- 包含句号

### 示例

| 好的示例 | 不好的示例 |
|---------|-----------|
| "App记录夜间打鼾声音" | "需要麦克风权限提供更好体验" |
| "输入密码继续" | "必须输入密码" |

---

## 预请求屏幕

### 用途

- 解释为什么需要权限
- 描述收集什么数据、如何使用
- 说明好处

### 注意事项

- 不提供授权激励
- 不镜像系统弹窗
- 重复目的文字

---

## 用户选择

### 尊重选择

- 允许拒绝后继续提供功能
- 不要因为拒绝惩罚用户

### 再次请求

- 使用深度链接到设置页面
- 提供上下文再次请求

---

## Android 适配

### 权限声明

```xml
<!-- AndroidManifest.xml -->
<uses-permission android:name="android.permission.CAMERA" />
<uses-permission android:name="android.permission.RECORD_AUDIO" />
<uses-permission android:name="android.permission.ACCESS_FINE_LOCATION" />
<uses-permission android:name="android.permission.READ_EXTERNAL_STORAGE" />
```

### 运行时权限

```kotlin
// 检查权限
if (ContextCompat.checkSelfPermission(this, Manifest.permission.CAMERA) 
    != PackageManager.PERMISSION_GRANTED) {
    // 请求权限
    ActivityCompat.requestPermissions(
        this,
        arrayOf(Manifest.permission.CAMERA),
        REQUEST_CODE_CAMERA
    )
}

// 处理结果
override fun onRequestPermissionsResult(
    requestCode: Int,
    permissions: Array<String>,
    grantResults: IntArray
) {
    when (requestCode) {
        REQUEST_CODE_CAMERA -> {
            if (grantResults.isNotEmpty() && grantResults[0] == PackageManager.PERMISSION_GRANTED) {
                // 权限 granted
            } else {
                // 权限 denied
            }
        }
    }
}
```

### 权限说明

```xml
<!-- strings.xml -->
<string name="camera_permission_rationale">需要相机权限来拍摄照片</string>
```

### 自定义权限对话框

```kotlin
// 显示说明对话框后请求权限
fun showCameraPermissionRationale() {
    AlertDialog.Builder(this)
        .setMessage(R.string.camera_permission_rationale)
        .setPositiveButton("继续") { _, _ ->
            requestCameraPermission()
        }
        .setNegativeButton("取消", null)
        .show()
}
```

### 应用隐私标签

```kotlin
// 在应用商店显示隐私信息
// 在 Play Console 中配置数据安全部分
```

### 深链接到设置

```kotlin
// 打开应用设置页面
fun openAppSettings() {
    Intent(Settings.ACTION_APPLICATION_DETAILS_SETTINGS).apply {
        data = Uri.fromParts("package", packageName, null)
        startActivity(this)
    }
}
```
