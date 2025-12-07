---
来源：https://developer.apple.com/documentation/SwiftUI/VisualEffect/scaleEffect(_:锚:)
抓取时间： 2025-12-03T06:29:50Z
---

# scaleEffect(_:anchor:)

**实例方法**

相对于锚点，按指定因子均匀地缩放该视图。

## 声明

```swift
func scaleEffect(_ s: CGFloat, anchor: UnitPoint3D = .center) -> some VisualEffect

```

## 参数

- **s**：该视图的比例因子。
- **anchor**：缩放视图的锚点。默认为居中。

## 返回值

将视图在所有维度上缩放 `s` 的效果。

## 讨论

缩放内容后，视图的原始尺寸将保持不变。要改变视图的尺寸，请使用`frame()` 这样的修改器。

## 缩放

- **scaleEffect(x:y:anchor:)**：根据给定的水平和垂直值，相对于锚点缩放视图的渲染输出。
- **scaleEffect(x:y:z:anchor:)**：根据指定的水平、垂直和深度因子，相对于锚点缩放该视图。


---
source: https://developer.apple.com/documentation/SwiftUI/VisualEffect/scaleEffect(_:anchor:)
crawled: 2025-12-03T06:29:50Z
---

# scaleEffect(_:anchor:)

**Instance Method**

Scales this view uniformly by the specified factor, relative to an anchor point.

## Declaration

```swift
func scaleEffect(_ s: CGFloat, anchor: UnitPoint3D = .center) -> some VisualEffect

```

## Parameters

- **s**: The scale factor for this view.
- **anchor**: The anchor point about which to scale the view. Defaults to center.

## Return Value

An effect that scales this view by `s` in all dimensions.

## Discussion

The original dimensions of the view are considered to be unchanged by scaling the contents. To change the dimensions of the view, use a modifier like `frame()` instead.

## Scaling

- **scaleEffect(x:y:anchor:)**: Scales the view’s rendered output by the given horizontal and vertical amounts, relative to an anchor point.
- **scaleEffect(x:y:z:anchor:)**: Scales this view by the specified horizontal, vertical, and depth factors, relative to an anchor point.

