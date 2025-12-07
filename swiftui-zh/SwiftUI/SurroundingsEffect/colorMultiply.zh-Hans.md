---
来源： https://developer.apple.com/documentation/SwiftUI/SurroundingsEffect/colorMultiply(_:)
抓取时间： 2025-12-03T06:08:37Z
---

# colorMultiply(_:)

**类型方法**

通过将透传视频与[Color](../Color.zh-Hans.md)相乘，为透传视频应用自定义色调的效果。

## 声明

```swift
static func colorMultiply(_ color: Color) -> SurroundingsEffect
```

## 参数

- **color**：要使透传偏向的颜色。颜色的不透明度将被忽略。使用扩展色彩空间增亮透射。

## 讨论

当您想在显示特定视图时对穿透进行着色时，请将[preferredSurroundingsEffect(_:)](../View/preferredsurroundingseffect.zh-Hans.md) 视图修改器与此功能一起使用。系统可能会限制透射中每种颜色的增亮或减暗程度。`Color.black`将导致不可见穿透，而`Color.white`则没有影响。`Color(red: 1.15, green: 1.0, blue: 1.0)` 将使透射中的红色增亮 15%。只有在打开沉浸式空间时才会应用此效果。


---
source: https://developer.apple.com/documentation/SwiftUI/SurroundingsEffect/colorMultiply(_:)
crawled: 2025-12-03T06:08:37Z
---

# colorMultiply(_:)

**Type Method**

An effect that applies a custom tint to the passthrough video by multiplying the passthrough with a [Color](../Color.zh-Hans.md).

## Declaration

```swift
static func colorMultiply(_ color: Color) -> SurroundingsEffect
```

## Parameters

- **color**: The color to bias the passthrough toward. The opacity of the color is ignored. Use the extended color space to brighten the passthrough.

## Discussion

Use this with the [preferredSurroundingsEffect(_:)](../View/preferredsurroundingseffect.zh-Hans.md) view modifier when you want to tint the passthrough while displaying a particular view. The system may decide to limit how much each color in the passthrough can be brightened or darkened. `Color.black` will cause no passthrough to be visible, and `Color.white` will have no effect. `Color(red: 1.15, green: 1.0, blue: 1.0)` would brighten the red in the passthrough by 15 percent. This effect will only be applied while an immersive space is opened.

