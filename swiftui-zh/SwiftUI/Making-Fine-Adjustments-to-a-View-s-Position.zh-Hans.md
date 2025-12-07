--- 来源：https://developer.apple.com/documentation/SwiftUI/Making-Fine-Adjustments-to-a-View-s-Position

抓取时间：2025-12-02T17:38:41Z

---

# 微调视图位置

**Article**

通过应用偏移或位置修饰符来移动视图的位置。

## 概述

使用 SwiftUI 自适应地布局和定位视图。如果仅使用组合无法实现设计，可以使用视图修饰符来微调布局。添加偏移修饰符可将视图的渲染内容从其当前位置移动，或添加位置修饰符可在其父视图中设置明确的位置。

### 创建视图布局

以下示例提供了一个视图，用于演示如何定位视图，并提供了一个在 [ZStack](ZStack.zh-Hans.md) 中组合的视图的粗略布局。该堆栈包含一个象限，象限内叠加了一个圆形图像：

```swift
struct Crosshairs: View { ... } // Draws crosshairs.

struct Quadrant: View {
    var body: some View {
        ZStack {
            Crosshairs()
            Rectangle()
                .stroke(Color.primary)
            Image(systemName: "circle")
        }
        .frame(width: 160, height: 160)
    }
}
```

有关使用堆栈组合视图的更多详细信息，请参阅 [Building-Layouts-with-Stack-Views](Building-Layouts-with-Stack-Views.zh-Hans.md)。

### 调整视图内容的位置

使用偏移修饰符可以微调圆在象限内的位置，从而调整父视图放置圆的位置。偏移修饰符会将图像从其默认中心位置偏移。例如，[offset(x:y:)](View/offset_x_y.zh-Hans.md) 修饰符使用 `x` 和 `y` 参数来表示视图坐标空间中的相对位置。

在 SwiftUI 中，视图的坐标空间使用 `x` 表示水平方向，使用 `y` 表示垂直方向。 `x` 的值从视图前缘的 `0` 开始，并随着位置向视图后缘移动而递增。`y` 的值从视图上缘的 `0` 开始，并随着位置向视图下缘移动而递增。不要假设前缘始终位于左侧，因为它会随布局方向而变化。当布局方向设置为从右到左时，`0` 的水平值位于视图的右侧。

下图显示了从左到右布局方向的坐标系，以矩形为基准，原点位于顶部前角：

以下示例将圆点 `40` 从中心向上移动到后缘：

```swift
struct Quadrant: View {
    var body: some View {
        ZStack {
            Crosshairs()
            Rectangle()
                .stroke(Color.primary)
            Image(systemName: "circle")
                .offset(x: 40.0, y: -40.0)
        }
        .frame(width: 160, height: 160)
    }
}
```

### 显式定位视图内容

要显式定位视图中的元素，请使用视图修饰符 [position(x:y:)](View/position_x_y.zh-Hans.md)。位置修饰符会覆盖父视图放置内容的位置。与偏移修饰符（它会将视图从父视图选择的位置偏移）不同，位置修饰符会将视图渲染到相对于父视图原点的位置。位置修饰符使用与偏移修饰符相同的坐标系 `x`、`y`，并且同样不会影响视图的大小。在本例中，圆的位置被设定在象限右侧中间偏下的位置，具体数值如下：

```swift
struct Quadrant: View {
    var body: some View {
        ZStack {
            Crosshairs()
            Rectangle()
                .stroke(Color.primary)
            Image(systemName: "circle")
                .position(x: 144, y: 80)
        }
        .frame(width: 160, height: 160)
    }
}
```

## 调整视图位置

- **position(_:)**：将此视图的中心定位到其父视图坐标空间中的指定点。

- **position(x:y:)**：将此视图的中心定位到其父视图坐标空间中的指定坐标。

- **offset(_:)**：将此视图水平和垂直偏移指定偏移量（偏移量由 offset 参数指定）。

- **offset(x:y:)**：将此视图水平和垂直偏移指定距离。

- **offset(z:)**：将视图沿 Z 轴向前移动指定距离（以点为单位）。


---
source: https://developer.apple.com/documentation/SwiftUI/Making-Fine-Adjustments-to-a-View-s-Position
crawled: 2025-12-02T17:38:41Z
---

# Making fine adjustments to a view’s position

**Article**

Shift the position of a view by applying the offset or position modifier.

## Overview

Use SwiftUI to adaptively lay out and position your views. If you can’t achieve your design with composition alone, fine tune the layout with view modifiers. Add an offset modifier to shift the rendered content of a view from its current position, or a position modifier to set an explicit position within its parent.

### Create a view layout

The following example provides a view to illustrate how to position views, providing a rough layout of views composed within a [ZStack](ZStack.zh-Hans.md). The stack contains a quadrant with an overlaid circle image:

```swift
struct Crosshairs: View { ... } // Draws crosshairs.

struct Quadrant: View {
    var body: some View {
        ZStack {
            Crosshairs()
            Rectangle()
                .stroke(Color.primary)
            Image(systemName: "circle")
        }
        .frame(width: 160, height: 160)
    }
}
```



For more detail on composing views with stacks, see [Building-Layouts-with-Stack-Views](Building-Layouts-with-Stack-Views.zh-Hans.md).

### Shift the location of a view’s content

Fine-tune the position of the circle within the quadrant by using an offset modifier to shift where the parent view places the circle. An offset modifier shifts the image from its default center position. For example, the [offset(x:y:)](View/offset_x_y.zh-Hans.md) modifier uses the parameters of `x` and `y` to represent a relative location within the view’s coordinate space.

In SwiftUI, the view’s coordinate space uses `x` to represent a horizontal direction and `y` to represent a vertical direction. The value of `x` starts at `0` at the leading edge of a view, and increases as the location moves toward the trailing edge of a view. The value of `y` starts at `0` at the top edge of a view, and increases as the location moves toward the bottom edge of a view. Don’t assume the leading edge is always on the left, because it changes with the layout direction. When the layout direction is set to right-to-left, the `0` horizontal value is on the right side of the view.

The following diagram shows the coordinates in the left-to-right layout direction against a rectangle, with the origin at the top, leading corner:



The following example shifts the circle `40` points from the center, up and toward the trailing edge:

```swift
struct Quadrant: View {
    var body: some View {
        ZStack {
            Crosshairs()
            Rectangle()
                .stroke(Color.primary)
            Image(systemName: "circle")
                .offset(x: 40.0, y: -40.0)
        }
        .frame(width: 160, height: 160)
    }
}
```



### Position view content explicitly

To explicitly position elements within a view, use the [position(x:y:)](View/position_x_y.zh-Hans.md) view modifier. A position modifier overrides where the parent view places its content. The modifier renders the view at a location offset from the origin of the parent view, unlike an offset modifier that shifts the view from the location chosen by the parent view. The position modifier uses the same `x`, `y` coordinate system as the offset modifier, and similarly doesn’t influence the size of the view. In this example, the position of the circle is set halfway down on the right side of the quadrant with explicit values:

```swift
struct Quadrant: View {
    var body: some View {
        ZStack {
            Crosshairs()
            Rectangle()
                .stroke(Color.primary)
            Image(systemName: "circle")
                .position(x: 144, y: 80)
        }
        .frame(width: 160, height: 160)
    }
}
```



## Adjusting a view’s position

- **position(_:)**: Positions the center of this view at the specified point in its parent’s coordinate space.
- **position(x:y:)**: Positions the center of this view at the specified coordinates in its parent’s coordinate space.
- **offset(_:)**: Offset this view by the horizontal and vertical amount specified in the offset parameter.
- **offset(x:y:)**: Offset this view by the specified horizontal and vertical distances.
- **offset(z:)**: Brings a view forward in Z by the provided distance in points.

