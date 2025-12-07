--- 来源：https://developer.apple.com/documentation/SwiftUI/HoverEffectContent/scaleEffect(_:anchor:)

抓取时间：2025-12-01T11:35:03Z

---

# scaleEffect(_:anchor:)

**实例方法**

根据给定的锚点，将视图的渲染输出在水平和垂直方向上按指定比例缩放。

## 声明

```swift
func scaleEffect(_ scale: CGFloat, anchor: UnitPoint = .center) -> some HoverEffectContent

```

## 参数

- **scale**：视图在水平和垂直方向上的缩放比例。

- **anchor**：定义视图中应用变换位置的点（默认值为 [center](../UnitPoint/center.zh-Hans.md)）。

## 返回值

一种可以缩放视图渲染输出的效果。


---
source: https://developer.apple.com/documentation/SwiftUI/HoverEffectContent/scaleEffect(_:anchor:)
crawled: 2025-12-01T11:35:03Z
---

# scaleEffect(_:anchor:)

**Instance Method**

Scales the view’s rendered output by the given amount in both the horizontal and vertical directions, relative to an anchor point.

## Declaration

```swift
func scaleEffect(_ scale: CGFloat, anchor: UnitPoint = .center) -> some HoverEffectContent

```

## Parameters

- **scale**: The amount to scale the view in the view in both the horizontal and vertical directions.
- **anchor**: The point with a default of [center](../UnitPoint/center.zh-Hans.md) that defines the location within the view from which to apply the transformation.

## Return Value

An effect that scales the view’s rendered output.

