--- 来源：https://developer.apple.com/documentation/SwiftUI/View/offset(_:)

抓取时间：2025-11-30T21:23:48Z

---

# offset(_:)

**实例方法**

根据 offset 参数指定的水平和垂直偏移量，将此视图偏移。

## 声明

```swift
nonisolated func offset(_ offset: CGSize) -> some View

```

## 参数

- **offset**：要偏移此视图的距离。

## 返回值

一个偏移了 `offset` 的视图。

## 说明

使用 `offset(_:)` 可以按 `offset` 参数指定的量移动显示的内容。

偏移内容不会改变视图的原始尺寸；在以下示例中，此视图绘制的灰色边框包围了文本的原始位置：

```swift
Text("Offset by passing CGSize()")
    .border(Color.green)
    .offset(CGSize(width: 20, height: 25))
    .border(Color.gray)
```

## 调整视图位置

- **对视图位置进行微调**：通过应用偏移或位置修改器来移动视图的位置。

- **position(_:)**：将此视图的中心定位到其父视图坐标空间中的指定点。

- **position(x:y:)**：将此视图的中心定位到其父视图坐标空间中的指定坐标。

- **offset(x:y:)**：按指定的水平和垂直距离偏移此视图。

- **offset(z:)**：将视图沿 Z 轴向前移动指定的点数距离。


---
source: https://developer.apple.com/documentation/SwiftUI/View/offset(_:)
crawled: 2025-11-30T21:23:48Z
---

# offset(_:)

**Instance Method**

Offset this view by the horizontal and vertical amount specified in the offset parameter.

## Declaration

```swift
nonisolated func offset(_ offset: CGSize) -> some View

```

## Parameters

- **offset**: The distance to offset this view.

## Return Value

A view that offsets this view by `offset`.

## Discussion

Use `offset(_:)` to shift the displayed contents by the amount specified in the `offset` parameter.

The original dimensions of the view aren’t changed by offsetting the contents; in the example below the gray border drawn by this view surrounds the original position of the text:

```swift
Text("Offset by passing CGSize()")
    .border(Color.green)
    .offset(CGSize(width: 20, height: 25))
    .border(Color.gray)
```



## Adjusting a view’s position

- **Making fine adjustments to a view’s position**: Shift the position of a view by applying the offset or position modifier.
- **position(_:)**: Positions the center of this view at the specified point in its parent’s coordinate space.
- **position(x:y:)**: Positions the center of this view at the specified coordinates in its parent’s coordinate space.
- **offset(x:y:)**: Offset this view by the specified horizontal and vertical distances.
- **offset(z:)**: Brings a view forward in Z by the provided distance in points.

