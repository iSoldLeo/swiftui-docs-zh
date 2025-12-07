--- 来源：https://developer.apple.com/documentation/SwiftUI/View/offset(z:)

抓取时间：2025-12-02T17:38:44Z

---

# offset(z:)

**实例方法**

将视图沿 Z 轴向前移动指定的距离（以点为单位）。

## 声明

```swift
nonisolated func offset(z: CGFloat) -> some View

```

## 返回值

沿 Z 轴向前移动 `distance` 的视图。

## 调整视图的位置

- **对视图位置进行微调**：通过应用偏移或位置修饰符来移动视图的位置。

- **position(_:)**：将此视图的中心定位到其父视图坐标空间中的指定点。

- **position(x:y:)**：将此视图的中心定位到其父视图坐标空间中的指定坐标。

- **offset(_:)**：按偏移参数指定的水平和垂直偏移量偏移此视图。

- **offset(x:y:)**：按指定的水平和垂直距离偏移此视图。


---
source: https://developer.apple.com/documentation/SwiftUI/View/offset(z:)
crawled: 2025-12-02T17:38:44Z
---

# offset(z:)

**Instance Method**

Brings a view forward in Z by the provided distance in points.

## Declaration

```swift
nonisolated func offset(z: CGFloat) -> some View

```

## Return Value

A view that is extruded forward in Z by `distance`.

## Adjusting a view’s position

- **Making fine adjustments to a view’s position**: Shift the position of a view by applying the offset or position modifier.
- **position(_:)**: Positions the center of this view at the specified point in its parent’s coordinate space.
- **position(x:y:)**: Positions the center of this view at the specified coordinates in its parent’s coordinate space.
- **offset(_:)**: Offset this view by the horizontal and vertical amount specified in the offset parameter.
- **offset(x:y:)**: Offset this view by the specified horizontal and vertical distances.

