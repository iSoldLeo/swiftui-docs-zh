--- 来源：https://developer.apple.com/documentation/SwiftUI/ImmersionStyle/progressive(aspectRatio:)

抓取时间：2025-12-01T10:22:30Z

---

# progressive(aspectRatio:)

**类型方法**

一种沉浸式样式，用于显示无边界内容，部分替换透传视频。

## 声明

```swift
static func progressive(aspectRatio: ProgressiveImmersionAspectRatio) -> ProgressiveImmersionStyle
```

## 参数

- **aspectRatio**：门户的宽高比。

## 说明

使用 [immersionStyle(selection:in:)](../Scene/immersionStyle_selection_in.zh-Hans.md) 场景修改器为 [ImmersiveSpace](../ImmersiveSpace.zh-Hans.md) 指定此样式。

沉浸式样式会影响窗口与环境中虚拟对象的交互方式。在 `progressive` 沉浸式模式下，无论用户如何调整窗口或虚拟内容的位置，窗口始终显示在虚拟内容的前方。这有助于用户在关闭透视功能时避免忽略虚拟内容后方的窗口。

系统初始使用一种传送门效果，在部分视野范围内替代透视功能。用户可以通过旋转数码表冠来交互式地调整传送门的大小，从应用程序定义的最小沉浸度调整到应用程序定义的最大沉浸度。


---
source: https://developer.apple.com/documentation/SwiftUI/ImmersionStyle/progressive(aspectRatio:)
crawled: 2025-12-01T10:22:30Z
---

# progressive(aspectRatio:)

**Type Method**

An immersion style that displays unbounded content that partially replaces passthrough video.

## Declaration

```swift
static func progressive(aspectRatio: ProgressiveImmersionAspectRatio) -> ProgressiveImmersionStyle
```

## Parameters

- **aspectRatio**: The aspect ratio of the portal.

## Discussion

Use the [immersionStyle(selection:in:)](../Scene/immersionStyle_selection_in.zh-Hans.md) scene modifier to specify this style for an [ImmersiveSpace](../ImmersiveSpace.zh-Hans.md).

The immersion style affects how windows interact with virtual objects in the environment. In `progressive` immersion, windows always render in front of virtual content, no matter how someone positions the window or the content. This helps people to avoid losing track of windows behind virtual content when passthrough is off.

The system initially uses a portal effect that replaces passthrough in a portion of the field of view. People can interactively adjust the size of the portal by rotating the Digital Crown, including down to a minimum amount of immersion defined by the app and up to the defined maximum amount of immersion.

