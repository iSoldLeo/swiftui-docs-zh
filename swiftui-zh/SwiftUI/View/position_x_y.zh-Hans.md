--- 来源：https://developer.apple.com/documentation/SwiftUI/View/position(x:y:)

抓取时间：2025-12-02T17:38:42Z

---

# position(x:y:)

**实例方法**

将此视图的中心定位到其父视图坐标系中的指定坐标。

## 声明

```swift
nonisolated func position(x: CGFloat = 0, y: CGFloat = 0) -> some View

```

## 参数

- **x**：此视图中心的 x 坐标。

- **y**：此视图中心的 y 坐标。

## 返回值

一个将此视图的中心固定在 `x` 和 `y` 处的视图。

## 讨论

使用 `position(x:y:)` 修改器，通过 `x` 和 `y` 偏移量，将视图中心放置在父视图中的特定坐标处。

```swift
Text("Position by passing the x and y coordinates")
    .position(x: 175, y: 100)
    .border(Color.gray)
```

## 调整视图位置

- **对视图位置进行微调**：通过应用偏移或位置修改器来移动视图的位置。

- **position(_:)**：将此视图的中心定位到其父视图坐标空间中的指定点。

- **offset(_:)**：按偏移参数中指定的水平和垂直量偏移此视图。

- **offset(x:y:)**：按指定的水平和垂直距离偏移此视图。

- **offset(z:)**：将视图沿 Z 轴向前移动指定距离（以点为单位）。


---
source: https://developer.apple.com/documentation/SwiftUI/View/position(x:y:)
crawled: 2025-12-02T17:38:42Z
---

# position(x:y:)

**Instance Method**

Positions the center of this view at the specified coordinates in its parent’s coordinate space.

## Declaration

```swift
nonisolated func position(x: CGFloat = 0, y: CGFloat = 0) -> some View

```

## Parameters

- **x**: The x-coordinate at which to place the center of this view.
- **y**: The y-coordinate at which to place the center of this view.

## Return Value

A view that fixes the center of this view at `x` and `y`.

## Discussion

Use the `position(x:y:)` modifier to place the center of a view at a specific coordinate in the parent view using an `x` and `y` offset.

```swift
Text("Position by passing the x and y coordinates")
    .position(x: 175, y: 100)
    .border(Color.gray)
```

## Adjusting a view’s position

- **Making fine adjustments to a view’s position**: Shift the position of a view by applying the offset or position modifier.
- **position(_:)**: Positions the center of this view at the specified point in its parent’s coordinate space.
- **offset(_:)**: Offset this view by the horizontal and vertical amount specified in the offset parameter.
- **offset(x:y:)**: Offset this view by the specified horizontal and vertical distances.
- **offset(z:)**: Brings a view forward in Z by the provided distance in points.

