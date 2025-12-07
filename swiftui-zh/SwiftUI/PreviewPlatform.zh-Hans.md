--- 来源：https://developer.apple.com/documentation/SwiftUI/PreviewPlatform
抓取时间：2025-12-02T17:45:57Z

---

# PreviewPlatform

**Enumeration**

可运行预览的平台。

## 声明

```swift
enum PreviewPlatform
```

## 概述

Xcode 会根据当前选择的目标推断预览的平台。如果您有一个多平台目标，并且想要为预览建议一个特定的目标，请实现 [platform](PreviewProvider/platform.zh-Hans.md) 计算属性作为提示，并指定以下预览平台之一：

```swift
struct CircleImage_Previews: PreviewProvider {
    static var previews: some View {
        CircleImage()
    }

    static var platform: PreviewPlatform? {
        PreviewPlatform.tvOS
    }
}
```

## 获取操作系统

- **PreviewPlatform.iOS**：指定 iOS 作为预览平台。

- **PreviewPlatform.macOS**：指定 macOS 作为预览平台。

- **PreviewPlatform.tvOS**：指定 tvOS 作为预览平台。

- **PreviewPlatform.watchOS**：指定 watchOS 作为预览平台。

## 定义预览

- **Previewable()**：允许动态属性以内联方式显示在预览中的标签。

- **PreviewProvider**：在 Xcode 中生成视图预览的类型。

- **previewDisplayName(_:)**：设置要在预览画布中显示的用户可见名称。

- **PreviewModifier**：定义预览可以显示的环境的类型。

- **PreviewModifierContent**：预览的已擦除类型信息的内容。

## 符合以下标准

- 可复制

- 可等价比较

- 可哈希

- 可发送

- 可发送元数据


---
source: https://developer.apple.com/documentation/SwiftUI/PreviewPlatform
crawled: 2025-12-02T17:45:57Z
---

# PreviewPlatform

**Enumeration**

Platforms that can run the preview.

## Declaration

```swift
enum PreviewPlatform
```

## Overview

Xcode infers the platform for a preview based on the currently selected target. If you have a multiplatform target and want to suggest a particular target for a preview, implement the [platform](PreviewProvider/platform.zh-Hans.md) computed property as a hint, and specify one of the preview platforms:

```swift
struct CircleImage_Previews: PreviewProvider {
    static var previews: some View {
        CircleImage()
    }

    static var platform: PreviewPlatform? {
        PreviewPlatform.tvOS
    }
}
```

## Getting an operating system

- **PreviewPlatform.iOS**: Specifies iOS as the preview platform.
- **PreviewPlatform.macOS**: Specifies macOS as the preview platform.
- **PreviewPlatform.tvOS**: Specifies tvOS as the preview platform.
- **PreviewPlatform.watchOS**: Specifies watchOS as the preview platform.

## Defining a preview

- **Previewable()**: Tag allowing a dynamic property to appear inline in a preview.
- **PreviewProvider**: A type that produces view previews in Xcode.
- **previewDisplayName(_:)**: Sets a user visible name to show in the canvas for a preview.
- **PreviewModifier**: A type that defines an environment in which previews can appear.
- **PreviewModifierContent**: The type-erased content of a preview.

## Conforms To

- Copyable
- Equatable
- Hashable
- Sendable
- SendableMetatype

