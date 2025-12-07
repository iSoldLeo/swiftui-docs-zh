---
来源： https://developer.apple.com/documentation/SwiftUI/Shape/size(_:anchor:)
抓取时间： 2025-12-02T21:42:06Z
---

# size(_:anchor:)

**实例方法**

返回表示相同形状的新版本的 self，但不在容器大小的范围内，而在`size` 的矩形范围内。

## 声明

```swift
nonisolated func size(_ size: CGSize, anchor: UnitPoint) -> some Shape

```

## 参数

- **size**：约束形状的尺寸。
- **anchor**：用于确定如何定位新形状的锚点。

## 返回值

一个新形状，约束于给定的 `size`，并使用 `anchor`定位。

## 讨论

当路径的边界和容器的边界不相等时，`anchor` 参数决定形状在容器中的定位方式。这不会影响根据形状创建的任何视图的布局属性（例如通过填充）。


---
source: https://developer.apple.com/documentation/SwiftUI/Shape/size(_:anchor:)
crawled: 2025-12-02T21:42:06Z
---

# size(_:anchor:)

**Instance Method**

Returns a new version of self representing the same shape, but within a rect of `size` instead of the container size.

## Declaration

```swift
nonisolated func size(_ size: CGSize, anchor: UnitPoint) -> some Shape

```

## Parameters

- **size**: The size to constrain the shape to.
- **anchor**: The anchor to use to determine how to position the new shape.

## Return Value

A new shape constrained to the given `size`, and positioned using `anchor`.

## Discussion

The `anchor` parameter determines how the shape will be positioned within the container when the path’s bounds and the container’s bounds are not equal. This does not affect the layout properties of any views created from the shape (e.g. by filling it).

