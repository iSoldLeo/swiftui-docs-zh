--- 来源：https://developer.apple.com/documentation/SwiftUI/View/offset(x:y:)

抓取时间：2025-12-02T17:38:44Z

---

# offset(x:y:)

**实例方法**

按指定的水平和垂直距离偏移此视图。

## 声明

```swift
nonisolated func offset(x: CGFloat = 0, y: CGFloat = 0) -> some View

```

## 参数

- **x**：要偏移此视图的水平距离。

- **y**：要偏移此视图的垂直距离。

## 返回值

一个偏移了 `x` 和 `y` 的视图。

## 讨论

使用 `offset(x:y:)` 将显示的内容按 `x` 和 `y` 参数指定的量进行偏移。

偏移内容不会改变视图的原始尺寸；在下面的示例中，此视图绘制的灰色边框包围了文本的原始位置：

```swift
Text("Offset by passing horizontal & vertical distance")
    .border(Color.green)
    .offset(x: 20, y: 50)
    .border(Color.gray)
```

## 调整视图的位置

- **对视图位置进行微调**：通过应用偏移或位置修改器来移动视图的位置。

- **position(_:)**：将此视图的中心定位到其父视图坐标空间中的指定点。

- **position(x:y:)**：将此视图的中心定位到其父视图坐标空间中的指定坐标。

- **offset(_:)**：按偏移参数指定的水平和垂直量偏移此视图。

- **offset(z:)**：按指定的点数将视图沿 Z 轴向前移动指定距离。


---
source: https://developer.apple.com/documentation/SwiftUI/View/offset(x:y:)
crawled: 2025-12-02T17:38:44Z
---

# offset(x:y:)

**Instance Method**

Offset this view by the specified horizontal and vertical distances.

## Declaration

```swift
nonisolated func offset(x: CGFloat = 0, y: CGFloat = 0) -> some View

```

## Parameters

- **x**: The horizontal distance to offset this view.
- **y**: The vertical distance to offset this view.

## Return Value

A view that offsets this view by `x` and `y`.

## Discussion

Use `offset(x:y:)` to shift the displayed contents by the amount specified in the `x` and `y` parameters.

The original dimensions of the view aren’t changed by offsetting the contents; in the example below the gray border drawn by this view surrounds the original position of the text:

```swift
Text("Offset by passing horizontal & vertical distance")
    .border(Color.green)
    .offset(x: 20, y: 50)
    .border(Color.gray)
```



## Adjusting a view’s position

- **Making fine adjustments to a view’s position**: Shift the position of a view by applying the offset or position modifier.
- **position(_:)**: Positions the center of this view at the specified point in its parent’s coordinate space.
- **position(x:y:)**: Positions the center of this view at the specified coordinates in its parent’s coordinate space.
- **offset(_:)**: Offset this view by the horizontal and vertical amount specified in the offset parameter.
- **offset(z:)**: Brings a view forward in Z by the provided distance in points.

