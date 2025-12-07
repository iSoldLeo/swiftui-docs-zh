--- 来源：https://developer.apple.com/documentation/SwiftUI/ShapeStyle/in(_:)

抓取时间：2025-12-03T06:25:28Z

---

# in(_:)

**实例方法**

将形状样式的单位空间坐标映射到给定矩形的绝对坐标。

## 声明

```swift
func `in`(_ rect: CGRect) -> some ShapeStyle

```

## 参数

- **rect**：一个矩形，用于提供形状样式映射的绝对坐标。

## 返回值

一个映射到 `rect` 所给出坐标的新形状样式。

## 讨论

某些形状样式的颜色或图案会根据 [UnitPoint](../UnitPoint.zh-Hans.md) 坐标随位置变化。例如，您可以创建一个以 [top](../UnitPoint/top.zh-Hans.md) 和 [bottom](../UnitPoint/bottom.zh-Hans.md) 为起点和终点的 [LinearGradient](../LinearGradient.zh-Hans.md)：

```swift
let gradient = LinearGradient(
    colors: [.red, .yellow],
    startPoint: .top,
    endPoint: .bottom)
```

渲染此类样式时，SwiftUI 会将单位空间坐标映射到填充形状的绝对坐标。但是，您可以通过向 `in(_:)` 方法提供一个矩形来告诉 SwiftUI 使用不同的坐标集。考虑两个使用上述渐变的可调整大小的矩形：

```swift
HStack {
    Rectangle()
        .fill(gradient)
    Rectangle()
        .fill(gradient.in(CGRect(x: 0, y: 0, width: 0, height: 300)))
}
.onTapGesture { isBig.toggle() }
.frame(height: isBig ? 300 : 50)
.animation(.easeInOut)
```

当 `isBig` 为真时（在其他地方定义为私有变量 [State](../State.zh-Hans.md)），这两个矩形看起来相同，因为它们的高度与修改后的渐变高度相匹配：

当用户点击 [HStack](../HStack.zh-Hans.md) 切换 `isBig` 时，矩形会缩小，但每个矩形的渐变响应方式不同：

SwiftUI 会将第一个矩形的渐变重新映射到新的框架高度，因此即使在较小的区域内，您仍然可以看到完整的颜色范围。对于第二个矩形，修改后的渐变仍然映射到整个高度，因此您只能看到整体渐变的一小部分。动画有助于直观地展示这种差异。


---
source: https://developer.apple.com/documentation/SwiftUI/ShapeStyle/in(_:)
crawled: 2025-12-03T06:25:28Z
---

# in(_:)

**Instance Method**

Maps a shape style’s unit-space coordinates to the absolute coordinates of a given rectangle.

## Declaration

```swift
func `in`(_ rect: CGRect) -> some ShapeStyle

```

## Parameters

- **rect**: A rectangle that gives the absolute coordinates over which to map the shape style.

## Return Value

A new shape style mapped to the coordinates given by `rect`.

## Discussion

Some shape styles have colors or patterns that vary with position based on [UnitPoint](../UnitPoint.zh-Hans.md) coordinates. For example, you can create a [LinearGradient](../LinearGradient.zh-Hans.md) using [top](../UnitPoint/top.zh-Hans.md) and [bottom](../UnitPoint/bottom.zh-Hans.md) as the start and end points:

```swift
let gradient = LinearGradient(
    colors: [.red, .yellow],
    startPoint: .top,
    endPoint: .bottom)
```

When rendering such styles, SwiftUI maps the unit space coordinates to the absolute coordinates of the filled shape. However, you can tell SwiftUI to use a different set of coordinates by supplying a rectangle to the `in(_:)` method. Consider two resizable rectangles using the gradient defined above:

```swift
HStack {
    Rectangle()
        .fill(gradient)
    Rectangle()
        .fill(gradient.in(CGRect(x: 0, y: 0, width: 0, height: 300)))
}
.onTapGesture { isBig.toggle() }
.frame(height: isBig ? 300 : 50)
.animation(.easeInOut)
```

When `isBig` is true — defined elsewhere as a private [State](../State.zh-Hans.md) variable — the rectangles look the same, because their heights match that of the modified gradient:



When the user toggles `isBig` by tapping the [HStack](../HStack.zh-Hans.md), the rectangles shrink, but the gradients each react in a different way:



SwiftUI remaps the gradient of the first rectangle to the new frame height, so that you continue to see the full range of colors in a smaller area. For the second rectangle, the modified gradient retains a mapping to the full height, so you instead see only a small part of the overall gradient. Animation helps to visualize the difference.

