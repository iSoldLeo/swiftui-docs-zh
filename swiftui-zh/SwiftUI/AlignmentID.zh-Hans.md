--- 来源：https://developer.apple.com/documentation/SwiftUI/AlignmentID
抓取时间：2025-12-02T17:38:51Z

---

# AlignmentID

**Protocol**

用于创建自定义对齐参考线的类型。

## 声明

```swift
protocol AlignmentID
```

## 概述

每个内置对齐参考线（如 [top](VerticalAlignment/top.zh-Hans.md) 或 [leading](HorizontalAlignment/leading.zh-Hans.md)）都定义为静态属性，并具有唯一的对齐标识符类型，用于生成该参考线的默认偏移量。要创建自定义对齐参考线，请将您自己的对齐标识符定义为符合 `AlignmentID` 协议的类型，并实现所需的 [defaultValue(in:)](AlignmentID/defaultValue_in.zh-Hans.md) 方法：

```swift
private struct FirstThirdAlignment: AlignmentID {
    static func defaultValue(in context: ViewDimensions) -> CGFloat {
        context.height / 3
    }
}
```

实现此方法时，请计算参考线相对于视图原点的默认偏移量。如有需要，您可以在计算中使用 [ViewDimensions](ViewDimensions.zh-Hans.md) 输入中的信息。此参数提供有关使用该参考线的特定视图的上下文信息。上面的示例创建了一个名为 `FirstThirdAlignment` 的标识符，并计算出一个默认值，该值是对齐视图高度的三分之一。

使用该标识符的类型，在某个对齐参考线类型（例如 [VerticalAlignment](VerticalAlignment.zh-Hans.md)）的扩展中创建一个静态属性：

```swift
extension VerticalAlignment {
    static let firstThird = VerticalAlignment(FirstThirdAlignment.self)
}
```

您可以像应用任何内置参考线一样应用您的自定义参考线。例如，您可以使用 [HStack](HStack.zh-Hans.md) 来根据上述定义的参考线，将视图对齐到其高度的三分之一处：

```swift
struct StripesGroup: View {
    var body: some View {
        HStack(alignment: .firstThird, spacing: 1) {
            HorizontalStripes().frame(height: 60)
            HorizontalStripes().frame(height: 120)
            HorizontalStripes().frame(height: 90)
        }
    }
}

struct HorizontalStripes: View {
    var body: some View {
        VStack(spacing: 1) {
            ForEach(0..<3) { _ in Color.blue }
        }
    }
}
```

由于每组条纹都由三个大小相等、垂直堆叠的矩形组成，因此它们会与顶部矩形的底边对齐。这对应于从每组条纹顶部原点测量的总高度的三分之一：

您还可以使用 [alignmentGuide(_:computeValue:)](View/alignmentGuide___computeValue.zh-Hans.md) 视图修改器来更改视图的自定义参考线的行为，就像更改内置参考线一样。例如，您可以更改上例中的一组条纹，使其参考线 `firstThird` 位于高度的三分之二处：

```swift
struct StripesGroupModified: View {
    var body: some View {
        HStack(alignment: .firstThird, spacing: 1) {
            HorizontalStripes().frame(height: 60)
            HorizontalStripes().frame(height: 120)
            HorizontalStripes().frame(height: 90)
                .alignmentGuide(.firstThird) { context in
                    2 * context.height / 3
                }
        }
    }
}
```

修改后的参考线计算方式会使受影响的视图将其中间矩形的底边放置在参考线 `firstThird` 上，该参考线与另外两组中顶部矩形的底边对齐：

## 获取默认值

- **defaultValue(in:)**：计算指定上下文中相应参考线的默认值。

## 对齐视图

- **在同一堆叠内对齐视图**：使用对齐参考线定位堆叠内的视图。

- **跨堆叠对齐视图**：创建自定义对齐方式并使用它来对齐多个堆叠中的视图。

- **alignmentGuide(_:computeValue:)**：设置视图的水平对齐方式。

- **Alignment**：沿两个轴的对齐方式。

- **HorizontalAlignment**：沿水平轴的对齐位置。

- **VerticalAlignment**：沿垂直轴的对齐位置。

- **DepthAlignment**：沿深度轴的对齐位置。

- **ViewDimensions**：视图在其自身坐标空间中的大小和对齐方式。

- **ViewDimensions3D**：视图在其自身坐标空间中 3D 的大小和对齐方式。

- **SpatialContainer**：用于在 3D 空间中对齐重叠内容的布局容器。


---
source: https://developer.apple.com/documentation/SwiftUI/AlignmentID
crawled: 2025-12-02T17:38:51Z
---

# AlignmentID

**Protocol**

A type that you use to create custom alignment guides.

## Declaration

```swift
protocol AlignmentID
```

## Overview

Every built-in alignment guide that [VerticalAlignment](VerticalAlignment.zh-Hans.md) or [HorizontalAlignment](HorizontalAlignment.zh-Hans.md) defines as a static property, like [top](VerticalAlignment/top.zh-Hans.md) or [leading](HorizontalAlignment/leading.zh-Hans.md), has a unique alignment identifier type that produces the default offset for that guide. To create a custom alignment guide, define your own alignment identifier as a type that conforms to the `AlignmentID` protocol, and implement the required [defaultValue(in:)](AlignmentID/defaultValue_in.zh-Hans.md) method:

```swift
private struct FirstThirdAlignment: AlignmentID {
    static func defaultValue(in context: ViewDimensions) -> CGFloat {
        context.height / 3
    }
}
```

When implementing the method, calculate the guide’s default offset from the view’s origin. If it’s helpful, you can use information from the [ViewDimensions](ViewDimensions.zh-Hans.md) input in the calculation. This parameter provides context about the specific view that’s using the guide. The above example creates an identifier called `FirstThirdAlignment` and calculates a default value that’s one-third of the height of the aligned view.

Use the identifier’s type to create a static property in an extension of one of the alignment guide types, like [VerticalAlignment](VerticalAlignment.zh-Hans.md):

```swift
extension VerticalAlignment {
    static let firstThird = VerticalAlignment(FirstThirdAlignment.self)
}
```

You can apply your custom guide like any of the built-in guides. For example, you can use an [HStack](HStack.zh-Hans.md) to align its views at one-third of their height using the guide defined above:

```swift
struct StripesGroup: View {
    var body: some View {
        HStack(alignment: .firstThird, spacing: 1) {
            HorizontalStripes().frame(height: 60)
            HorizontalStripes().frame(height: 120)
            HorizontalStripes().frame(height: 90)
        }
    }
}

struct HorizontalStripes: View {
    var body: some View {
        VStack(spacing: 1) {
            ForEach(0..<3) { _ in Color.blue }
        }
    }
}
```

Because each set of stripes has three equal, vertically stacked rectangles, they align at the bottom edge of the top rectangle. This corresponds in each case to a third of the overall height, as measured from the origin at the top of each set of stripes:



You can also use the [alignmentGuide(_:computeValue:)](View/alignmentGuide___computeValue.zh-Hans.md) view modifier to alter the behavior of your custom guide for a view, as you might alter a built-in guide. For example, you can change one of the stacks of stripes from the previous example to align its `firstThird` guide at two thirds of the height instead:

```swift
struct StripesGroupModified: View {
    var body: some View {
        HStack(alignment: .firstThird, spacing: 1) {
            HorizontalStripes().frame(height: 60)
            HorizontalStripes().frame(height: 120)
            HorizontalStripes().frame(height: 90)
                .alignmentGuide(.firstThird) { context in
                    2 * context.height / 3
                }
        }
    }
}
```

The modified guide calculation causes the affected view to place the bottom edge of its middle rectangle on the `firstThird` guide, which aligns with the bottom edge of the top rectangle in the other two groups:



## Getting the default value

- **defaultValue(in:)**: Calculates a default value for the corresponding guide in the specified context.

## Aligning views

- **Aligning views within a stack**: Position views inside a stack using alignment guides.
- **Aligning views across stacks**: Create a custom alignment and use it to align views across multiple stacks.
- **alignmentGuide(_:computeValue:)**: Sets the view’s horizontal alignment.
- **Alignment**: An alignment in both axes.
- **HorizontalAlignment**: An alignment position along the horizontal axis.
- **VerticalAlignment**: An alignment position along the vertical axis.
- **DepthAlignment**: An alignment position along the depth axis.
- **ViewDimensions**: A view’s size and alignment guides in its own coordinate space.
- **ViewDimensions3D**: A view’s 3D size and alignment guides in its own coordinate space.
- **SpatialContainer**: A layout container that aligns overlapping content in 3D space.

