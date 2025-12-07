--- 来源：https://developer.apple.com/documentation/SwiftUI/ViewDimensions

抓取时间：2025-12-02T17:38:51Z

---

# ViewDimensions

**Structure**

视图在其自身坐标空间中的尺寸和对齐参考线。

## 声明

```swift
struct ViewDimensions
```

## 概述

此结构包含视图的尺寸和对齐参考线。您将收到此结构的实例，用于各种布局计算，例如：

- 定义自定义对齐参考线的默认值；请参阅 [defaultValue(in:)](AlignmentID/defaultValue_in.zh-Hans.md)。

- 修改视图上的对齐参考线；请参阅 [alignmentGuide(_:computeValue:)](View/alignmentGuide___computeValue.zh-Hans.md)。

- 请求自定义视图布局的子视图的尺寸；请参阅 [dimensions(in:)](LayoutSubview/dimensions_in.zh-Hans.md)。

### 自定义对齐参考线

您可以通过两种方式获取此结构的实例：一种是作为您实现的 [defaultValue(in:)](AlignmentID/defaultValue_in.zh-Hans.md) 方法的 `context` 参数，用于生成对齐参考线的默认偏移量；另一种是作为您提供给 [alignmentGuide(_:computeValue:)](View/alignmentGuide___computeValue.zh-Hans.md) 视图修改器的闭包的第一个参数，用于覆盖对齐参考线的默认计算方法。在这两种情况下，您都可以根据需要使用此实例来计算参考线的偏移量。例如，您可以计算自定义 [VerticalAlignment](VerticalAlignment.zh-Hans.md) 的默认偏移量，该偏移量是视图 [height](ViewDimensions/height.zh-Hans.md) 的分数：

```swift
private struct FirstThirdAlignment: AlignmentID {
    static func defaultValue(in context: ViewDimensions) -> CGFloat {
        context.height / 3
    }
}

extension VerticalAlignment {
    static let firstThird = VerticalAlignment(FirstThirdAlignment.self)
}
```

再举一个例子，您可以使用视图尺寸实例查找现有参考线的偏移量并对其进行修改：

```swift
struct ViewDimensionsOffset: View {
    var body: some View {
        VStack(alignment: .leading) {
            Text("Default")
            Text("Indented")
                .alignmentGuide(.leading) { context in
                    context[.leading] - 10
                }
        }
    }
}
```

上面的示例缩进了第二个文本视图，因为减法运算会将第二个文本视图的前导参考线沿 x 轴负方向移动，也就是在视图坐标系中向左移动。因此，SwiftUI 会将第二个文本视图相对于第一个文本视图向右移动，以保持它们的前导参考线对齐：

### 布局方向

上面的讨论描述的是从左到右的语言环境，但您无需更改参考线的计算方式即可在从右到左的环境中运行。SwiftUI 会将视图的原点从视图的左侧移动到右侧，并反转 x 轴正方向。因此，现有计算方法会产生相同的效果，但方向相反。

您可以通过使用 [environment(_:_:)](View/environment.zh-Hans.md) 修改器设置上面定义的视图的 [layoutDirection](EnvironmentValues/layoutDirection.zh-Hans.md) 属性来验证这一点：

```swift
ViewDimensionsOffset()
    .environment(\.layoutDirection, .rightToLeft)
```

在参考线不变的情况下，这将产生预期的效果——相对于第一个文本视图的右侧，第二个文本视图的右侧会缩进。前缘现在位于右侧，偏移方向也相反：

## 获取尺寸

- **height**：视图的高度。

- **width**：视图的宽度。

## 访问参考线值

- **subscript(_:)**：获取给定水平参考线的值。

- **subscript(explicit:)**：获取给定水平对齐参考线的显式值。

## 对齐视图

- **在堆栈内对齐视图**：使用对齐参考线定位堆栈内的视图。

- **跨堆栈对齐视图**：创建自定义对齐方式，并使用它来对齐多个堆栈中的视图。

- **alignmentGuide(_:computeValue:)**：设置视图的水平对齐方式。

- **Alignment**：沿两个轴的对齐方式。

- **HorizontalAlignment**：沿水平轴的对齐位置。

- **VerticalAlignment**：沿垂直轴的对齐位置。

- **DepthAlignment**：沿深度轴的对齐位置。

- **AlignmentID**：用于创建自定义对齐参考线的类型。

- **ViewDimensions3D**：视图在其自身坐标空间中的三维尺寸和对齐指南。

- **SpatialContainer**：用于在三维空间中对齐重叠内容的布局容器。

## 符合以下规范

- 可复制

- 可等值化


---
source: https://developer.apple.com/documentation/SwiftUI/ViewDimensions
crawled: 2025-12-02T17:38:51Z
---

# ViewDimensions

**Structure**

A view’s size and alignment guides in its own coordinate space.

## Declaration

```swift
struct ViewDimensions
```

## Overview

This structure contains the size and alignment guides of a view. You receive an instance of this structure to use in a variety of layout calculations, like when you:

- Define a default value for a custom alignment guide; see [defaultValue(in:)](AlignmentID/defaultValue_in.zh-Hans.md).
- Modify an alignment guide on a view; see [alignmentGuide(_:computeValue:)](View/alignmentGuide___computeValue.zh-Hans.md).
- Ask for the dimensions of a subview of a custom view layout; see [dimensions(in:)](LayoutSubview/dimensions_in.zh-Hans.md).

### Custom alignment guides

You receive an instance of this structure as the `context` parameter to the [defaultValue(in:)](AlignmentID/defaultValue_in.zh-Hans.md) method that you implement to produce the default offset for an alignment guide, or as the first argument to the closure you provide to the [alignmentGuide(_:computeValue:)](View/alignmentGuide___computeValue.zh-Hans.md) view modifier to override the default calculation for an alignment guide. In both cases you can use the instance, if helpful, to calculate the offset for the guide. For example, you could compute a default offset for a custom [VerticalAlignment](VerticalAlignment.zh-Hans.md) as a fraction of the view’s [height](ViewDimensions/height.zh-Hans.md):

```swift
private struct FirstThirdAlignment: AlignmentID {
    static func defaultValue(in context: ViewDimensions) -> CGFloat {
        context.height / 3
    }
}

extension VerticalAlignment {
    static let firstThird = VerticalAlignment(FirstThirdAlignment.self)
}
```

As another example, you could use the view dimensions instance to look up the offset of an existing guide and modify it:

```swift
struct ViewDimensionsOffset: View {
    var body: some View {
        VStack(alignment: .leading) {
            Text("Default")
            Text("Indented")
                .alignmentGuide(.leading) { context in
                    context[.leading] - 10
                }
        }
    }
}
```

The example above indents the second text view because the subtraction moves the second text view’s leading guide in the negative x direction, which is to the left in the view’s coordinate space. As a result, SwiftUI moves the second text view to the right, relative to the first text view, to keep their leading guides aligned:



### Layout direction

The discussion above describes a left-to-right language environment, but you don’t change your guide calculation to operate in a right-to-left environment. SwiftUI moves the view’s origin from the left to the right side of the view and inverts the positive x direction. As a result, the existing calculation produces the same effect, but in the opposite direction.

You can see this if you use the [environment(_:_:)](View/environment.zh-Hans.md) modifier to set the [layoutDirection](EnvironmentValues/layoutDirection.zh-Hans.md) property for the view that you defined above:

```swift
ViewDimensionsOffset()
    .environment(\.layoutDirection, .rightToLeft)
```

With no change in your guide, this produces the desired effect — it indents the second text view’s right side, relative to the first text view’s right side. The leading edge is now on the right, and the direction of the offset is reversed:



## Getting dimensions

- **height**: The view’s height.
- **width**: The view’s width.

## Accessing guide values

- **subscript(_:)**: Gets the value of the given horizontal guide.
- **subscript(explicit:)**: Gets the explicit value of the given horizontal alignment guide.

## Aligning views

- **Aligning views within a stack**: Position views inside a stack using alignment guides.
- **Aligning views across stacks**: Create a custom alignment and use it to align views across multiple stacks.
- **alignmentGuide(_:computeValue:)**: Sets the view’s horizontal alignment.
- **Alignment**: An alignment in both axes.
- **HorizontalAlignment**: An alignment position along the horizontal axis.
- **VerticalAlignment**: An alignment position along the vertical axis.
- **DepthAlignment**: An alignment position along the depth axis.
- **AlignmentID**: A type that you use to create custom alignment guides.
- **ViewDimensions3D**: A view’s 3D size and alignment guides in its own coordinate space.
- **SpatialContainer**: A layout container that aligns overlapping content in 3D space.

## Conforms To

- Copyable
- Equatable

