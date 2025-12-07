---
来源：https://developer.apple.com/documentation/SwiftUI/SurroundingsEffect/dim(强度:)
抓取时间： 2025-12-01T10:57:38Z
---

# dim(intensity:)

**类型方法**

一种效果，可按自定义量调暗穿透视频。

## 声明

```swift
static func dim(intensity: Double) -> SurroundingsEffect
```

## 讨论

当您想在显示特定视图时使穿透变暗时，请将[preferredSurroundingsEffect(_:)](../View/preferredsurroundingseffect.zh-Hans.md)视图修改器与此功能一起使用。该值将在 0 和 1 之间箝位。该效果仅在打开沉浸式空间时应用。


---
source: https://developer.apple.com/documentation/SwiftUI/SurroundingsEffect/dim(intensity:)
crawled: 2025-12-01T10:57:38Z
---

# dim(intensity:)

**Type Method**

An effect that dims the passthrough video a custom amount.

## Declaration

```swift
static func dim(intensity: Double) -> SurroundingsEffect
```

## Discussion

Use this with the [preferredSurroundingsEffect(_:)](../View/preferredsurroundingseffect.zh-Hans.md) view modifier when you want to darken the passthrough while displaying a particular view. The value will be clamped between 0 and 1. This effect will only be applied while an immersive space is opened.

