--- 来源：https://developer.apple.com/documentation/SwiftUI/VerticalAlignment
抓取时间：2025-12-02T17:38:49Z

---

# VerticalAlignment

**Structure**

沿垂直轴的对齐位置。

## 声明

```swift
@frozen struct VerticalAlignment
```

## 概述

使用垂直对齐参考线可以垂直定位视图，例如在 [HStack](HStack.zh-Hans.md) 中并排放置视图，或者使用 [GridRow](GridRow.zh-Hans.md) 在 [Grid](Grid.zh-Hans.md) 中创建一行视图。以下示例演示了常见的内置垂直对齐方式：

您可以通过创建一系列以水平堆栈形式实现的行来生成上述示例，并为每个堆栈配置不同的对齐参考线：

```swift
private struct VerticalAlignmentGallery: View {
    var body: some View {
        VStack(spacing: 30) {
            row(alignment: .top, text: "Top")
            row(alignment: .center, text: "Center")
            row(alignment: .bottom, text: "Bottom")
            row(alignment: .firstTextBaseline, text: "First Text Baseline")
            row(alignment: .lastTextBaseline, text: "Last Text Baseline")
        }
    }

    private func row(alignment: VerticalAlignment, text: String) -> some View {
        HStack(alignment: alignment, spacing: 0) {
            Color.red.frame(height: 1)
            Text(text).font(.title).border(.gray)
            Color.red.frame(height: 1)
        }
    }
}
```

在布局过程中，SwiftUI 会将每个堆栈内的视图对齐，方法是将受影响视图的指定参考线对齐。SwiftUI 会根据视图的特征计算特定视图的参考线位置。例如，[center](VerticalAlignment/center.zh-Hans.md) 参考线出现在视图高度的一半处。您可以使用 [alignmentGuide(_:computeValue:)](View/alignmentGuide___computeValue.zh-Hans.md) 视图修饰符来覆盖特定视图的参考线计算。

### 文本基线对齐

使用 [firstTextBaseline](VerticalAlignment/firstTextBaseline.zh-Hans.md) 或 [lastTextBaseline](VerticalAlignment/lastTextBaseline.zh-Hans.md) 参考线分别与视图中包含的最顶部或最底部文本行的底部对齐。文本基线对齐会排除字符低于基线的部分，例如小写字母 g 和 j 的尾部：

```swift
row(alignment: .firstTextBaseline, text: "fghijkl")
```

如果对不包含任何文本的视图使用文本基线对齐，SwiftUI 会应用等效于 [bottom](VerticalAlignment/bottom.zh-Hans.md) 的对齐方式。例如，对于上例中的行，SwiftUI 会将水平线的底部与文本的基线对齐：

在许多情况下，例如创建表单时，将文本视图与其基线对齐而不是与其框架底部对齐可以获得最佳布局效果。例如，您可以将一个 [GridRow](GridRow.zh-Hans.md) 单元格中的描述性文本的基线与同一行中另一个单元格中的文本字段或复选框标签的基线对齐。

### 自定义对齐参考线

要创建自定义垂直对齐参考线，首先要创建一个符合 [AlignmentID](AlignmentID.zh-Hans.md) 协议的类型，然后使用该类型初始化 `VerticalAlignment` 上的一个新静态属性：

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

您需要实现 [defaultValue(in:)](AlignmentID/defaultValue_in.zh-Hans.md) 方法来计算自定义对齐参考线的默认值。该方法接收一个 [ViewDimensions](ViewDimensions.zh-Hans.md) 实例，您可以根据视图的特征计算该值。上面的示例将参考线放置在视图高度的三分之一处（从视图原点测量）。

然后，您可以像使用任何内置参考线一样使用自定义对齐参考线。例如，您可以将其用作 [HStack](HStack.zh-Hans.md) 的 `alignment` 参数，或者使用 [alignmentGuide(_:computeValue:)](View/alignmentGuide___computeValue.zh-Hans.md) 视图修改器来更改特定视图的参考线计算。

### 复合对齐

将 `VerticalAlignment` 与 [HorizontalAlignment](HorizontalAlignment.zh-Hans.md) 组合，即可创建一个复合 [Alignment](Alignment.zh-Hans.md)，该复合值同时指示垂直和水平定位。例如，您可以将上一节中的自定义 `firstThird` 垂直对齐与内置的 [center](HorizontalAlignment/center.zh-Hans.md) 水平对齐组合，用于 [ZStack](ZStack.zh-Hans.md)：

```swift
struct LayeredHorizontalStripes: View {
    var body: some View {
        ZStack(alignment: Alignment(horizontal: .center, vertical: .firstThird)) {
            horizontalStripes(color: .blue)
                .frame(width: 180, height: 90)
            horizontalStripes(color: .green)
                .frame(width: 70, height: 60)
        }
    }

    private func horizontalStripes(color: Color) -> some View {
        VStack(spacing: 1) {
            ForEach(0..<3) { _ in color }
        }
    }
}
```

上面的示例使用的宽度和高度会生成两组不匹配的三条垂直条纹。 [ZStack](ZStack.zh-Hans.md) 将两组元素水平居中，并垂直对齐，使它们分别位于每组元素顶部三分之一处。这样，每组元素顶部条纹的下边缘就会对齐：

## 获取参考线

- **top**：用于标记视图顶部边缘的参考线。

- **center**：用于标记视图垂直中心的参考线。

- **bottom**：用于标记视图底部边缘的参考线。

- **firstTextBaseline**：用于标记视图中最顶部文本基线的参考线。

- **lastTextBaseline**：用于标记视图中最底部文本基线的参考线。

## 创建自定义对齐方式

- **init(_:)**：创建指定类型的自定义垂直对齐方式。

- **combineExplicit(_:)**：合并此实例生成的一系列显式对齐值。

## 对齐视图

- **在堆栈内对齐视图**：使用对齐参考线在堆栈内定位视图。

- **跨堆栈对齐视图**：创建自定义对齐方式，并使用它来对齐多个堆栈中的视图。

- **alignmentGuide(_:computeValue:)**：设置视图的水平对齐方式。

- **Alignment**：在两个轴上进行对齐。

- **HorizontalAlignment**：沿水平轴的对齐位置。

- **DepthAlignment**：沿深度轴的对齐位置。

- **AlignmentID**：用于创建自定义对齐参考线的类型。

- **ViewDimensions**：视图在其自身坐标空间中的大小和对齐方式指南。

- **ViewDimensions3D**：视图在其自身坐标空间中 3D 大小和对齐方式指南。

- **SpatialContainer**：用于在 3D 空间中对齐重叠内容的布局容器。

## 符合以下规范

- 位可复制 (BitwiseCopyable)

- 可复制 (Copyable)

- 等值 (Equatable)

- 可发送 (Sendable)

- 可发送元类型 (SendableMetatype)


---
source: https://developer.apple.com/documentation/SwiftUI/VerticalAlignment
crawled: 2025-12-02T17:38:49Z
---

# VerticalAlignment

**Structure**

An alignment position along the vertical axis.

## Declaration

```swift
@frozen struct VerticalAlignment
```

## Overview

Use vertical alignment guides to position views relative to one another vertically, like when you place views side-by-side in an [HStack](HStack.zh-Hans.md) or when you create a row of views in a [Grid](Grid.zh-Hans.md) using [GridRow](GridRow.zh-Hans.md). The following example demonstrates common built-in vertical alignments:



You can generate the example above by creating a series of rows implemented as horizontal stacks, where you configure each stack with a different alignment guide:

```swift
private struct VerticalAlignmentGallery: View {
    var body: some View {
        VStack(spacing: 30) {
            row(alignment: .top, text: "Top")
            row(alignment: .center, text: "Center")
            row(alignment: .bottom, text: "Bottom")
            row(alignment: .firstTextBaseline, text: "First Text Baseline")
            row(alignment: .lastTextBaseline, text: "Last Text Baseline")
        }
    }

    private func row(alignment: VerticalAlignment, text: String) -> some View {
        HStack(alignment: alignment, spacing: 0) {
            Color.red.frame(height: 1)
            Text(text).font(.title).border(.gray)
            Color.red.frame(height: 1)
        }
    }
}
```

During layout, SwiftUI aligns the views inside each stack by bringing together the specified guides of the affected views. SwiftUI calculates the position of a guide for a particular view based on the characteristics of the view. For example, the [center](VerticalAlignment/center.zh-Hans.md) guide appears at half the height of the view. You can override the guide calculation for a particular view using the [alignmentGuide(_:computeValue:)](View/alignmentGuide___computeValue.zh-Hans.md) view modifier.

### Text baseline alignment

Use the [firstTextBaseline](VerticalAlignment/firstTextBaseline.zh-Hans.md) or [lastTextBaseline](VerticalAlignment/lastTextBaseline.zh-Hans.md) guide to match the bottom of either the top- or bottom-most line of text that a view contains, respectively. Text baseline alignment excludes the parts of characters that descend below the baseline, like the tail on lower case g and j:

```swift
row(alignment: .firstTextBaseline, text: "fghijkl")
```

If you use a text baseline alignment on a view that contains no text, SwiftUI applies the equivalent of [bottom](VerticalAlignment/bottom.zh-Hans.md) alignment instead. For the row in the example above, SwiftUI matches the bottom of the horizontal lines with the baseline of the text:



Aligning a text view to its baseline rather than to the bottom of its frame produces the best layout effect in many cases, like when creating forms. For example, you can align the baseline of descriptive text in one [GridRow](GridRow.zh-Hans.md) cell with the baseline of a text field, or the label of a checkbox, in another cell in the same row.

### Custom alignment guides

You can create a custom vertical alignment guide by first creating a type that conforms to the [AlignmentID](AlignmentID.zh-Hans.md) protocol, and then using that type to initialize a new static property on `VerticalAlignment`:

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

You implement the [defaultValue(in:)](AlignmentID/defaultValue_in.zh-Hans.md) method to calculate a default value for the custom alignment guide. The method receives a [ViewDimensions](ViewDimensions.zh-Hans.md) instance that you can use to calculate a value based on characteristics of the view. The example above places the guide at one-third of the height of the view as measured from the view’s origin.

You can then use the custom alignment guide like any built-in guide. For example, you can use it as the `alignment` parameter to an [HStack](HStack.zh-Hans.md), or to alter the guide calculation for a specific view using the [alignmentGuide(_:computeValue:)](View/alignmentGuide___computeValue.zh-Hans.md) view modifier.

### Composite alignment

Combine a `VerticalAlignment` with a [HorizontalAlignment](HorizontalAlignment.zh-Hans.md) to create a composite [Alignment](Alignment.zh-Hans.md) that indicates both vertical and horizontal positioning in one value. For example, you could combine your custom `firstThird` vertical alignment from the previous section with a built-in [center](HorizontalAlignment/center.zh-Hans.md) horizontal alignment to use in a [ZStack](ZStack.zh-Hans.md):

```swift
struct LayeredHorizontalStripes: View {
    var body: some View {
        ZStack(alignment: Alignment(horizontal: .center, vertical: .firstThird)) {
            horizontalStripes(color: .blue)
                .frame(width: 180, height: 90)
            horizontalStripes(color: .green)
                .frame(width: 70, height: 60)
        }
    }

    private func horizontalStripes(color: Color) -> some View {
        VStack(spacing: 1) {
            ForEach(0..<3) { _ in color }
        }
    }
}
```

The example above uses widths and heights that generate two mismatched sets of three vertical stripes. The [ZStack](ZStack.zh-Hans.md) centers the two sets horizontally and aligns them vertically one-third from the top of each set. This aligns the bottom edges of the top stripe from each set:



## Getting guides

- **top**: A guide that marks the top edge of the view.
- **center**: A guide that marks the vertical center of the view.
- **bottom**: A guide that marks the bottom edge of the view.
- **firstTextBaseline**: A guide that marks the top-most text baseline in a view.
- **lastTextBaseline**: A guide that marks the bottom-most text baseline in a view.

## Creating a custom alignment

- **init(_:)**: Creates a custom vertical alignment of the specified type.
- **combineExplicit(_:)**: Merges a sequence of explicit alignment values produced by this instance.

## Aligning views

- **Aligning views within a stack**: Position views inside a stack using alignment guides.
- **Aligning views across stacks**: Create a custom alignment and use it to align views across multiple stacks.
- **alignmentGuide(_:computeValue:)**: Sets the view’s horizontal alignment.
- **Alignment**: An alignment in both axes.
- **HorizontalAlignment**: An alignment position along the horizontal axis.
- **DepthAlignment**: An alignment position along the depth axis.
- **AlignmentID**: A type that you use to create custom alignment guides.
- **ViewDimensions**: A view’s size and alignment guides in its own coordinate space.
- **ViewDimensions3D**: A view’s 3D size and alignment guides in its own coordinate space.
- **SpatialContainer**: A layout container that aligns overlapping content in 3D space.

## Conforms To

- BitwiseCopyable
- Copyable
- Equatable
- Sendable
- SendableMetatype

