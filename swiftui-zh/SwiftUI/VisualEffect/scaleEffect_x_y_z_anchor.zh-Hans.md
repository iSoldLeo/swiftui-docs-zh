---
来源：https://developer.apple.com/documentation/SwiftUI/VisualEffect/scaleEffect(x:y:z:anchor:)
抓取时间：2025-12-03T06:29:52Z
---

# scaleEffect(x:y:z:anchor:)

**实例方法**

根据指定的水平、垂直和深度因子，相对于锚点缩放视图。

## 声明

```swift
func scaleEffect(x: CGFloat = 1.0, y: CGFloat = 1.0, z: CGFloat = 1.0, anchor: UnitPoint3D = .center) -> some VisualEffect

```

## 参数

- **x**：该视图的水平缩放系数。
- **y**：该视图的垂直比例因子。
- **z**：该视图的深度比例因子。
- **anchor**：缩放视图的锚点。默认为居中。

## 返回值

按 `x`、`y` 和 `z`缩放视图的效果。

### 讨论

缩放内容后，视图的原始尺寸将保持不变。要改变视图的尺寸，请使用`frame()` 这样的修改器。

## 缩放

- **scaleEffect(_:anchor:)**：相对于锚点，以指定的系数均匀地缩放该视图。
- **scaleEffect(x:y:anchor:)**：相对于锚点，按给定的水平和垂直量缩放视图的渲染输出。


---
source: https://developer.apple.com/documentation/SwiftUI/VisualEffect/scaleEffect(x:y:z:anchor:)
crawled: 2025-12-03T06:29:52Z
---

# scaleEffect(x:y:z:anchor:)

**Instance Method**

Scales this view by the specified horizontal, vertical, and depth factors, relative to an anchor point.

## Declaration

```swift
func scaleEffect(x: CGFloat = 1.0, y: CGFloat = 1.0, z: CGFloat = 1.0, anchor: UnitPoint3D = .center) -> some VisualEffect

```

## Parameters

- **x**: The horizontal scale factor for this view.
- **y**: The vertical scale factor for this view.
- **z**: The depth scale factor for this view.
- **anchor**: The anchor point about which to scale the view. Defaults to center.

## Return Value

An effect that scales this view by `x`,`y`, and `z`.

## Discussion

The original dimensions of the view are considered to be unchanged by scaling the contents. To change the dimensions of the view, use a modifier like `frame()` instead.

## Scaling

- **scaleEffect(_:anchor:)**: Scales this view uniformly by the specified factor, relative to an anchor point.
- **scaleEffect(x:y:anchor:)**: Scales the view’s rendered output by the given horizontal and vertical amounts, relative to an anchor point.

