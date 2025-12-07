---
来源： https://developer.apple.com/documentation/SwiftUI/GraphicsContext/ResolvedText/measure(in:)
抓取时间： 2025-12-01T22:05:20Z
---

# measure(in:)

**实例方法**

测量应放置文本的给定区域内已解析文本的大小。

## 声明

```swift
func measure(in size: CGSize) -> CGSize
```

## 参数

- **size**：要放置 [Text](../../Text.zh-Hans.md) 视图的区域。

## 获取文本属性

- **firstBaseline(in:)**：获取第一行升线到基线的距离。
- **lastBaseline(in:)**：获取第一行上升沿到最后一行基线的距离。
- **shading**：用于填充未着色文本区域的阴影。


---
source: https://developer.apple.com/documentation/SwiftUI/GraphicsContext/ResolvedText/measure(in:)
crawled: 2025-12-01T22:05:20Z
---

# measure(in:)

**Instance Method**

Measures the size of the resolved text for a given area into which the text should be placed.

## Declaration

```swift
func measure(in size: CGSize) -> CGSize
```

## Parameters

- **size**: The area to place the [Text](../../Text.zh-Hans.md) view in.

## Getting the text properties

- **firstBaseline(in:)**: Gets the distance from the first line’s ascender to its baseline.
- **lastBaseline(in:)**: Gets the distance from the first line’s ascender to the last line’s baseline.
- **shading**: The shading to fill uncolored text regions with.

