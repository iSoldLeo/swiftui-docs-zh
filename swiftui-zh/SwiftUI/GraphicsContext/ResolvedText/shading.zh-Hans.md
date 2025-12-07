---
来源： https://developer.apple.com/documentation/SwiftUI/GraphicsContext/ResolvedText/shading
抓取时间： 2025-12-03T17:20:02Z
---

# 阴影

**实例属性**

用于填充未着色文本区域的阴影。

## 声明

```swift
var shading: GraphicsContext.Shading
```

## 讨论

该值默认为[foreground](../Shading/foreground.zh-Hans.md)阴影。

## 获取文本属性

- **firstBaseline(in:)**：获取第一行升线到基线的距离。
- **lastBaseline(in:)**：获取第一行上升沿到最后一行基线的距离。
- **measure(in:)**：测量应放置文本的给定区域内已解析文本的大小。


---
source: https://developer.apple.com/documentation/SwiftUI/GraphicsContext/ResolvedText/shading
crawled: 2025-12-03T17:20:02Z
---

# shading

**Instance Property**

The shading to fill uncolored text regions with.

## Declaration

```swift
var shading: GraphicsContext.Shading
```

## Discussion

This value defaults to the [foreground](../Shading/foreground.zh-Hans.md) shading.

## Getting the text properties

- **firstBaseline(in:)**: Gets the distance from the first line’s ascender to its baseline.
- **lastBaseline(in:)**: Gets the distance from the first line’s ascender to the last line’s baseline.
- **measure(in:)**: Measures the size of the resolved text for a given area into which the text should be placed.

