--- 来源：https://developer.apple.com/documentation/SwiftUI/Aligning-Views-Within-a-Stack

抓取时间：2025-12-02T17:38:45Z

---

# 对齐堆栈中的视图

**Article**

使用对齐参考线在堆栈中定位视图。

## 概述

堆栈会根据其对齐方式放置子视图，默认对齐方式为居中对齐。初始化堆栈时，您可以指定堆栈使用的对齐方式，该对齐方式也适用于堆栈的子视图。如果要修改单个子视图的位置，请使用对齐参考线修饰符进行调整，使视图偏离堆栈提供的对齐方式。

要跨多个堆栈对齐视图，请参阅 [Aligning-Views-Across-Stacks](Aligning-Views-Across-Stacks.zh-Hans.md)。

### 使用默认基本对齐方式

要了解 SwiftUI 如何将默认对齐方式应用于 [HStack](HStack.zh-Hans.md) 中的视图，请查看以下用于为录制应用提供状态视图的代码示例。`HStack` 包含一个用于显示图标的图像视图和两个带有标签的文本视图，这些标签使用 [font(_:)](View/font.zh-Hans.md) 修饰符来调整文本的字体大小。

```swift
HStack {
    Image("microphone")
    Text("Connecting")
        .font(.caption)
    Text("Bryan")
        .font(.title)
}
.padding()
.border(Color.blue, width: 1)
```

下图中的橙色参考线显示了视图在堆栈中的默认对齐位置。该线在本文档中用作视觉参考。

### 自定义堆栈对齐方式

您可以根据堆栈支持的对齐方式提供的参考线来对齐堆栈中的内容。各种类型的堆栈支持以下对齐方式：

- [HStack](HStack.zh-Hans.md) 使用 [VerticalAlignment](VerticalAlignment.zh-Hans.md) 中定义的参考线。

- [VStack](VStack.zh-Hans.md) 使用 [HorizontalAlignment](HorizontalAlignment.zh-Hans.md) 中定义的引导线。

- [ZStack](ZStack.zh-Hans.md) 使用 [Alignment](Alignment.zh-Hans.md) 中定义的引导线，以及 `HorizontalAlignment` 和 `VerticalAlignment` 的组合。

初始化堆栈时，使用 `alignment` 参数定义堆栈的对齐引导线。以下示例将 `HStack` 的对齐方式设置为 [firstTextBaseline](VerticalAlignment/firstTextBaseline.zh-Hans.md)，使其子视图与第一个文本视图（包含字符串“Connecting”）的基线对齐：

```swift
HStack(alignment: .firstTextBaseline) {
    Image("microphone")
    Text("Connecting")
        .font(.caption)
    Text("Bryan")
        .font(.title)
}
.padding()
.border(Color.blue, width: 1)
```

### 调整堆栈中各个视图的对齐方式

自定义图像不提供文本基线参考线，因此图像底部会与文本视图的基线对齐。使用 [alignmentGuide(_:computeValue:)](View/alignmentGuide___computeValue.zh-Hans.md) 调整图像的对齐方式，以获得所需的视觉对齐效果。对齐参考线的闭包提供了一个 [ViewDimensions](ViewDimensions.zh-Hans.md) 的实例，在本例中为参数 `context`，您可以使用它来返回偏移值。从 `context` 和 [bottom](VerticalAlignment/bottom.zh-Hans.md) 中查找的值，提供了一个偏移量，用于将图像底部与堆栈上定义的基线参考线对齐，偏移量根据该偏移量进行调整：

```swift
HStack(alignment: .firstTextBaseline) {
    Image("microphone")
        .alignmentGuide(.firstTextBaseline) { context in
            context[.bottom] - 0.12 * context.height
        }
    Text("Connecting")
        .font(.caption)
    Text("Bryan")
        .font(.title)
}
.padding()
.border(Color.blue, width: 1)
```

使用对齐参考线修饰符时，请确保指定堆栈的活动对齐方式。否则，SwiftUI 将不会调用闭包来偏移视图。在上面的示例中，对齐参考线的输入 [firstTextBaseline](VerticalAlignment/firstTextBaseline.zh-Hans.md) 与堆栈的对齐方式匹配，因此调整会影响图像的位置：

### 使用 SF Symbols 简化与文本对齐的视图

您可以将麦克风图像替换为 [doc://com.apple.documentation/design/Human-Interface-Guidelines/sf-symbols] 中的类似图标，以简化视图。SF Symbols 中的图标使用文本基线参考线，这意味着它们支持您应用于视图的任何字体样式。

```swift
HStack(alignment: .firstTextBaseline) {
    Image(systemName: "mic.circle")
        .font(.title)
    Text("Connecting")
        .font(.caption)
    Text("Bryan")
        .font(.title)
}
.padding()
.border(Color.blue, width: 1)
```

## 对齐视图

- **跨堆栈对齐视图**：创建自定义对齐方式，并使用它来对齐多个堆栈中的视图。

- **alignmentGuide(_:computeValue:)**：设置视图的水平对齐方式。

- **Alignment**：在两个轴上对齐。

- **HorizontalAlignment**：沿水平轴的对齐位置。

- **VerticalAlignment**：沿垂直轴的对齐位置。

- **DepthAlignment**：沿深度轴的对齐位置。

- **AlignmentID**：用于创建自定义对齐参考线的类型。

- **ViewDimensions**：视图在其自身坐标空间中的大小和对齐参考线。

- **ViewDimensions3D**：视图在其自身坐标空间中的三维尺寸和对齐指南。

- **SpatialContainer**：用于在三维空间中对齐重叠内容的布局容器。


---
source: https://developer.apple.com/documentation/SwiftUI/Aligning-Views-Within-a-Stack
crawled: 2025-12-02T17:38:45Z
---

# Aligning views within a stack

**Article**

Position views inside a stack using alignment guides.

## Overview

Stacks place their child views to match their alignment, which defaults to center alignment. When you initialize the stack, you can specify an alignment for the stack to use that also applies to a stack’s child views. If you want to modify the placement of individual child views, use the alignment guide modifier to make adjustments that offset the view from the alignment the stack provides.

To align views across multiple stacks, see [Aligning-Views-Across-Stacks](Aligning-Views-Across-Stacks.zh-Hans.md).

### Use defaults for basic alignment

For an example of how SwiftUI applies default alignment to the views in an [HStack](HStack.zh-Hans.md), examine the following code used to provide a status view for a recording app. The `HStack` contains an image view for the icon and two text views with labels that use the [font(_:)](View/font.zh-Hans.md) modifier to adjust the font size of the text.

```swift
HStack {
    Image("microphone")
    Text("Connecting")
        .font(.caption)
    Text("Bryan")
        .font(.title)
}
.padding()
.border(Color.blue, width: 1)
```

The orange reference line in the following figure shows the default alignment position of the views within the stack. The line functions as a visual reference for the purposes of this article.



### Customize stack alignment

You can align content within a stack based on guides provided by the alignments that the stack supports. The various kinds of stacks support the following alignments:

- [HStack](HStack.zh-Hans.md) uses the guides defined in [VerticalAlignment](VerticalAlignment.zh-Hans.md).
- [VStack](VStack.zh-Hans.md) uses the guides defined in [HorizontalAlignment](HorizontalAlignment.zh-Hans.md).
- [ZStack](ZStack.zh-Hans.md) uses the guides defined in [Alignment](Alignment.zh-Hans.md), and a combination of `HorizontalAlignment` and `VerticalAlignment`.

Use the `alignment` parameter when initializing a stack to define the alignment guide for the stack. The following example sets the alignment of the `HStack` to [firstTextBaseline](VerticalAlignment/firstTextBaseline.zh-Hans.md), which aligns its child views to the baseline of the first text view (which contains the string “Connecting”):

```swift
HStack(alignment: .firstTextBaseline) {
    Image("microphone")
    Text("Connecting")
        .font(.caption)
    Text("Bryan")
        .font(.title)
}
.padding()
.border(Color.blue, width: 1)
```



### Adjust the alignment of individual views within a stack

Custom images don’t provide a text baseline guide, so the bottom of the image aligns to the text view’s baseline. Adjust the alignment of the image using [alignmentGuide(_:computeValue:)](View/alignmentGuide___computeValue.zh-Hans.md) to get the visual alignment you desire. The alignment guide’s closure provides an instance of [ViewDimensions](ViewDimensions.zh-Hans.md), the parameter `context` in this example — which you can use to return an offset value. The value looked up from `context` with [bottom](VerticalAlignment/bottom.zh-Hans.md), provides an offset that aligns the bottom of the image adjusted by an offset to the baseline guide defined on the stack:

```swift
HStack(alignment: .firstTextBaseline) {
    Image("microphone")
        .alignmentGuide(.firstTextBaseline) { context in
            context[.bottom] - 0.12 * context.height
        }
    Text("Connecting")
        .font(.caption)
    Text("Bryan")
        .font(.title)
}
.padding()
.border(Color.blue, width: 1)
```

When you use an alignment guide modifier, make sure to specify an active alignment of the stack. Otherwise, SwiftUI doesn’t invoke the closure to offset the view. In the example above, the [firstTextBaseline](VerticalAlignment/firstTextBaseline.zh-Hans.md) input to the alignment guide matches the stack’s alignment, so the adjustment affects the placement of the image:



### Use SF Symbols to simplify views when aligning with text

You can replace the microphone image with a similar icon from [doc://com.apple.documentation/design/Human-Interface-Guidelines/sf-symbols] to simplify the view. The icons from SF Symbols use text baseline guides, which means they support whatever font styling you apply to the view.

```swift
HStack(alignment: .firstTextBaseline) {
    Image(systemName: "mic.circle")
        .font(.title)
    Text("Connecting")
        .font(.caption)
    Text("Bryan")
        .font(.title)
}
.padding()
.border(Color.blue, width: 1)
```



## Aligning views

- **Aligning views across stacks**: Create a custom alignment and use it to align views across multiple stacks.
- **alignmentGuide(_:computeValue:)**: Sets the view’s horizontal alignment.
- **Alignment**: An alignment in both axes.
- **HorizontalAlignment**: An alignment position along the horizontal axis.
- **VerticalAlignment**: An alignment position along the vertical axis.
- **DepthAlignment**: An alignment position along the depth axis.
- **AlignmentID**: A type that you use to create custom alignment guides.
- **ViewDimensions**: A view’s size and alignment guides in its own coordinate space.
- **ViewDimensions3D**: A view’s 3D size and alignment guides in its own coordinate space.
- **SpatialContainer**: A layout container that aligns overlapping content in 3D space.

