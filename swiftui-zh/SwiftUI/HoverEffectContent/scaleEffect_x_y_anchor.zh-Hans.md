--- 来源：https://developer.apple.com/documentation/SwiftUI/HoverEffectContent/scaleEffect(x:y:anchor:)

抓取时间：2025-12-01T11:35:04Z

---

# scaleEffect(x:y:anchor:)

**实例方法**

根据给定的水平和垂直比例，相对于锚点缩放视图的渲染输出。

## 声明

```swift
func scaleEffect(x: CGFloat = 1.0, y: CGFloat = 1.0, anchor: UnitPoint = .center) -> some HoverEffectContent

```

## 参数

- **x**：表示视图水平缩放比例的数值。默认值为 `1.0`。

- **y**：表示视图垂直缩放比例的数值。默认值为 `1.0`。

- **anchor**：默认值为 [center](../UnitPoint/center.zh-Hans.md) 的点，用于定义视图中应用变换的位置。

## 返回值

一种缩放视图渲染输出的效果。


---
source: https://developer.apple.com/documentation/SwiftUI/HoverEffectContent/scaleEffect(x:y:anchor:)
crawled: 2025-12-01T11:35:04Z
---

# scaleEffect(x:y:anchor:)

**Instance Method**

Scales the view’s rendered output by the given horizontal and vertical amounts, relative to an anchor point.

## Declaration

```swift
func scaleEffect(x: CGFloat = 1.0, y: CGFloat = 1.0, anchor: UnitPoint = .center) -> some HoverEffectContent

```

## Parameters

- **x**: An amount that represents the horizontal amount to scale the view. The default value is `1.0`.
- **y**: An amount that represents the vertical amount to scale the view. The default value is `1.0`.
- **anchor**: The point with a default of [center](../UnitPoint/center.zh-Hans.md) that defines the location within the view from which to apply the transformation.

## Return Value

An effect that scales the view’s rendered output.

