---
来源：https://developer.apple.com/documentation/SwiftUI/VisualEffect/scaleEffect(x:y:anchor:)
抓取时间： 2025-12-01T11:18:59Z
---

# scaleEffect(x:y:anchor:)

**实例方法**

根据给定的水平和垂直值，相对于锚点缩放视图的渲染输出。

## 声明

```swift
func scaleEffect(x: CGFloat = 1.0, y: CGFloat = 1.0, anchor: UnitPoint = .center) -> some VisualEffect

```

## 参数

- **x**：表示缩放视图的水平幅度的数值。默认值为 `1.0`。
- **y**：表示缩放视图的垂直方向的量。默认值为`1.0`。
- **anchor**：点，默认值为[center](../UnitPoint/center.zh-Hans.md)，它定义了应用变换的视图位置。

## 返回值

缩放视图渲染输出的效果。

## 缩放

- **scaleEffect(_:anchor:)**：相对于一个锚点，以指定的系数均匀地缩放该视图。
- **scaleEffect(x:y:z:anchor:)**：相对于锚点，按指定的水平、垂直和深度因子缩放此视图。


---
source: https://developer.apple.com/documentation/SwiftUI/VisualEffect/scaleEffect(x:y:anchor:)
crawled: 2025-12-01T11:18:59Z
---

# scaleEffect(x:y:anchor:)

**Instance Method**

Scales the view’s rendered output by the given horizontal and vertical amounts, relative to an anchor point.

## Declaration

```swift
func scaleEffect(x: CGFloat = 1.0, y: CGFloat = 1.0, anchor: UnitPoint = .center) -> some VisualEffect

```

## Parameters

- **x**: An amount that represents the horizontal amount to scale the view. The default value is `1.0`.
- **y**: An amount that represents the vertical amount to scale the view. The default value is `1.0`.
- **anchor**: The point with a default of [center](../UnitPoint/center.zh-Hans.md) that defines the location within the view from which to apply the transformation.

## Return Value

An effect that scales the view’s rendered output.

## Scaling

- **scaleEffect(_:anchor:)**: Scales this view uniformly by the specified factor, relative to an anchor point.
- **scaleEffect(x:y:z:anchor:)**: Scales this view by the specified horizontal, vertical, and depth factors, relative to an anchor point.

