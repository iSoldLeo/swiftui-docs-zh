--- 来源：https://developer.apple.com/documentation/SwiftUI/View/position(_:)

抓取时间：2025-11-30T21:23:46Z

---

# position(_:)

**实例方法**

将此视图的中心定位到其父视图坐标空间中的指定点。

## 声明

```swift
nonisolated func position(_ position: CGPoint) -> some View

```

## 参数

- **position**：要放置此视图中心的点。

## 返回值

一个将此视图的中心固定在 `position` 的视图。

## 讨论

使用 `position(_:)` 修改器，通过 [doc://com.apple.documentation/documentation/CoreFoundation/CGPoint] 指定 `x` 和 `y` 偏移量，将视图中心放置在父视图中的特定坐标处。

```swift
Text("Position by passing a CGPoint()")
    .position(CGPoint(x: 175, y: 100))
    .border(Color.gray)
```

## 调整视图位置

- **对视图位置进行微调**：通过应用偏移或位置修改器来移动视图的位置。

- **position(x:y:)**：将此视图的中心定位到其父视图坐标空间中的指定坐标处。

- **offset(_:)**：按偏移参数中指定的水平和垂直量偏移此视图。

- **offset(x:y:)**：按指定的水平和垂直距离偏移此视图。 - **offset(z:)**：将视图沿 Z 轴向前移动指定距离（以点为单位）。


---
source: https://developer.apple.com/documentation/SwiftUI/View/position(_:)
crawled: 2025-11-30T21:23:46Z
---

# position(_:)

**Instance Method**

Positions the center of this view at the specified point in its parent’s coordinate space.

## Declaration

```swift
nonisolated func position(_ position: CGPoint) -> some View

```

## Parameters

- **position**: The point at which to place the center of this view.

## Return Value

A view that fixes the center of this view at `position`.

## Discussion

Use the `position(_:)` modifier to place the center of a view at a specific coordinate in the parent view using a [doc://com.apple.documentation/documentation/CoreFoundation/CGPoint] to specify the `x` and `y` offset.

```swift
Text("Position by passing a CGPoint()")
    .position(CGPoint(x: 175, y: 100))
    .border(Color.gray)
```

## Adjusting a view’s position

- **Making fine adjustments to a view’s position**: Shift the position of a view by applying the offset or position modifier.
- **position(x:y:)**: Positions the center of this view at the specified coordinates in its parent’s coordinate space.
- **offset(_:)**: Offset this view by the horizontal and vertical amount specified in the offset parameter.
- **offset(x:y:)**: Offset this view by the specified horizontal and vertical distances.
- **offset(z:)**: Brings a view forward in Z by the provided distance in points.

