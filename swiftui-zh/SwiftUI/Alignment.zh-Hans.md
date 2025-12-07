---
来源： https://developer.apple.com/documentation/SwiftUI/Alignment
抓取时间： 2025-12-02T17:38:48Z
---

# 对齐

**Structure**

双轴对齐。

## 声明

```swift
@frozen struct Alignment
```

## 概览

一个 `Alignment` 包含一个 [HorizontalAlignment](HorizontalAlignment.zh-Hans.md) 向导和一个 [VerticalAlignment](VerticalAlignment.zh-Hans.md) 向导。指定对齐方式可指导某些布局容器和修改器的行为，例如将视图放置在 [ZStack](ZStack.zh-Hans.md) 中，或分别使用 [overlay(alignment:content:)](View/overlay_alignment_content.zh-Hans.md) 或 [background(alignment:content:)](View/background_alignment_content.zh-Hans.md) 将视图分层到另一个视图的前面或后面。在布局过程中，SwiftUI 会将受影响视图的指定导轨靠拢，对齐视图。

SwiftUI 提供了一组内置对齐方式，代表内置水平和垂直对齐导向的常见组合。下图中的蓝色方框显示了每个方框标签所指定的相对于背景视图的对齐方式：



下面的代码生成了上图，其中每个蓝框都显示在一个配置了不同对齐方式的覆盖图中：

```swift
struct AlignmentGallery: View {
    var body: some View {
        BackgroundView()
            .overlay(alignment: .topLeading) { box(".topLeading") }
            .overlay(alignment: .top) { box(".top") }
            .overlay(alignment: .topTrailing) { box(".topTrailing") }
            .overlay(alignment: .leading) { box(".leading") }
            .overlay(alignment: .center) { box(".center") }
            .overlay(alignment: .trailing) { box(".trailing") }
            .overlay(alignment: .bottomLeading) { box(".bottomLeading") }
            .overlay(alignment: .bottom) { box(".bottom") }
            .overlay(alignment: .bottomTrailing) { box(".bottomTrailing") }
            .overlay(alignment: .leadingLastTextBaseline) { box(".leadingLastTextBaseline") }
            .overlay(alignment: .trailingFirstTextBaseline) { box(".trailingFirstTextBaseline") }
    }

    private func box(_ name: String) -> some View {
        Text(name)
            .font(.system(.caption, design: .monospaced))
            .padding(2)
            .foregroundColor(.white)
            .background(.blue.opacity(0.8), in: Rectangle())
    }
}

private struct BackgroundView: View {
    var body: some View {
        Grid(horizontalSpacing: 0, verticalSpacing: 0) {
            GridRow {
                Text("Some text in an upper quadrant")
                Color.gray.opacity(0.3)
            }
            GridRow {
                Color.gray.opacity(0.3)
                Text("More text in a lower quadrant")
            }
        }
        .aspectRatio(1, contentMode: .fit)
        .foregroundColor(.secondary)
        .border(.gray)
    }
}
```

为了避免拥挤，对齐方式图中只显示了两种可用的文本基线对齐方式。其他对齐方式如其名称所示。请注意，第一个文本基线对齐方式与背景视图中最顶端的文本行对齐，而最后一个文本基线对齐方式与最底端的文本行对齐。有关文本基线对齐的更多信息，请参阅[VerticalAlignment](VerticalAlignment.zh-Hans.md)。

在从左到右的语言（如英语）中，前导对齐方式和尾部对齐方式分别出现在左边缘和右边缘。在从右到左的语言环境中，SwiftUI 会反转对齐方式。有关更多信息，请参阅 [HorizontalAlignment](HorizontalAlignment.zh-Hans.md)。

### 自定义对齐方式

您可以使用 [init(horizontal:vertical:)](Alignment/init_horizontal_vertical.zh-Hans.md) 初始化器创建自定义对齐方式（通常是为了使用自定义水平或垂直向导）。例如，您可以将名为 `firstThird` 的自定义垂直导轨与内置的水平 [center](HorizontalAlignment/center.zh-Hans.md) 导轨结合起来，并使用它来配置 [ZStack](ZStack.zh-Hans.md)：

```swift
ZStack(alignment: Alignment(horizontal: .center, vertical: .firstThird)) {
    // ...
}
```

有关创建自定义向导的更多信息，包括上例中创建自定义`firstThird` 对齐方式的代码，请参阅[AlignmentID](AlignmentID.zh-Hans.md)。

## 获取顶部指南

- **topLeading**：标记视图顶部和前缘的导图。
- **top**：标记视图顶边的导标。
- **topTrailing**：标记视图顶部和尾部边缘的导轨。

## 获取中间向导

- **leading**：标记视图前缘的向导。
- **center**：标记视图中心的导标。
- **trailing**：标记视图尾部边缘的导标。

## 获取底部向导

- **bottomLeading**：标记视图底边和前缘的导轨。
- **bottom**：标记视图底边的导标。
- **bottomTrailing**：标记视图底部和尾部边缘的导轨。

## 获取文本基线向导

- **leadingFirstTextBaseline**：在视图中标记前缘和最顶部文本基线的向导。
- **centerFirstTextBaseline**：在视图中标记最上文本基线的引导线。
- **trailingFirstTextBaseline**：在视图中标记后缘和最上文本基线的向导。
- **leadingLastTextBaseline**：在视图中标记前缘和最下端文本基线的导标。
- **centerLastTextBaseline**：在视图中标记最下端文本基线的导标。
- **trailingLastTextBaseline**：在视图中标记尾部边缘和最底部文本基线的向导。

## 创建自定义对齐方式

- **init(horizontal:vertical:)**：使用指定的水平和垂直对齐方式创建自定义对齐方式值。
- **horizontal**：水平轴上的对齐方式。
- **vertical**：垂直轴上的对齐方式。

## 对齐视图

- 在堆叠内对齐视图**：使用对齐导向器在堆栈内定位视图。
- 跨堆栈对齐视图**：创建自定义对齐方式，并使用它在多个堆栈中对齐视图。
- **alignmentGuide(_:computeValue:)**：设置视图的水平对齐方式。
- **HorizontalAlignment**：沿水平轴的对齐位置。
- **VerticalAlignment**：沿垂直轴对齐的位置。
- **DepthAlignment**：沿深度轴的对齐位置。
- **AlignmentID**：用于创建自定义对齐导轨的类型。
- **ViewDimensions**：视图在其自身坐标空间中的尺寸和对齐方式向导。
- **ViewDimensions3D**：视图在其自身坐标空间中的三维尺寸和对齐向导。
- **SpatialContainer**：在三维空间中对齐重叠内容的布局容器。

## 符合

- 比特可复制
- 可复制
- 等价
- 可发送
- 可发送元类型


---
source: https://developer.apple.com/documentation/SwiftUI/Alignment
crawled: 2025-12-02T17:38:48Z
---

# Alignment

**Structure**

An alignment in both axes.

## Declaration

```swift
@frozen struct Alignment
```

## Overview

An `Alignment` contains a [HorizontalAlignment](HorizontalAlignment.zh-Hans.md) guide and a [VerticalAlignment](VerticalAlignment.zh-Hans.md) guide. Specify an alignment to direct the behavior of certain layout containers and modifiers, like when you place views in a [ZStack](ZStack.zh-Hans.md), or layer a view in front of or behind another view using [overlay(alignment:content:)](View/overlay_alignment_content.zh-Hans.md) or [background(alignment:content:)](View/background_alignment_content.zh-Hans.md), respectively. During layout, SwiftUI brings the specified guides of the affected views together, aligning the views.

SwiftUI provides a set of built-in alignments that represent common combinations of the built-in horizontal and vertical alignment guides. The blue boxes in the following diagram demonstrate the alignment named by each box’s label, relative to the background view:



The following code generates the diagram above, where each blue box appears in an overlay that’s configured with a different alignment:

```swift
struct AlignmentGallery: View {
    var body: some View {
        BackgroundView()
            .overlay(alignment: .topLeading) { box(".topLeading") }
            .overlay(alignment: .top) { box(".top") }
            .overlay(alignment: .topTrailing) { box(".topTrailing") }
            .overlay(alignment: .leading) { box(".leading") }
            .overlay(alignment: .center) { box(".center") }
            .overlay(alignment: .trailing) { box(".trailing") }
            .overlay(alignment: .bottomLeading) { box(".bottomLeading") }
            .overlay(alignment: .bottom) { box(".bottom") }
            .overlay(alignment: .bottomTrailing) { box(".bottomTrailing") }
            .overlay(alignment: .leadingLastTextBaseline) { box(".leadingLastTextBaseline") }
            .overlay(alignment: .trailingFirstTextBaseline) { box(".trailingFirstTextBaseline") }
    }

    private func box(_ name: String) -> some View {
        Text(name)
            .font(.system(.caption, design: .monospaced))
            .padding(2)
            .foregroundColor(.white)
            .background(.blue.opacity(0.8), in: Rectangle())
    }
}

private struct BackgroundView: View {
    var body: some View {
        Grid(horizontalSpacing: 0, verticalSpacing: 0) {
            GridRow {
                Text("Some text in an upper quadrant")
                Color.gray.opacity(0.3)
            }
            GridRow {
                Color.gray.opacity(0.3)
                Text("More text in a lower quadrant")
            }
        }
        .aspectRatio(1, contentMode: .fit)
        .foregroundColor(.secondary)
        .border(.gray)
    }
}
```

To avoid crowding, the alignment diagram shows only two of the available text baseline alignments. The others align as their names imply. Notice that the first text baseline alignment aligns with the top-most line of text in the background view, while the last text baseline aligns with the bottom-most line. For more information about text baseline alignment, see [VerticalAlignment](VerticalAlignment.zh-Hans.md).

In a left-to-right language like English, the leading and trailing alignments appear on the left and right edges, respectively. SwiftUI reverses these in right-to-left language environments. For more information, see [HorizontalAlignment](HorizontalAlignment.zh-Hans.md).

### Custom alignment

You can create custom alignments — which you typically do to make use of custom horizontal or vertical guides — by using the [init(horizontal:vertical:)](Alignment/init_horizontal_vertical.zh-Hans.md) initializer. For example, you can combine a custom vertical guide called `firstThird` with the built-in horizontal [center](HorizontalAlignment/center.zh-Hans.md) guide, and use it to configure a [ZStack](ZStack.zh-Hans.md):

```swift
ZStack(alignment: Alignment(horizontal: .center, vertical: .firstThird)) {
    // ...
}
```

For more information about creating custom guides, including the code that creates the custom `firstThird` alignment in the example above, see [AlignmentID](AlignmentID.zh-Hans.md).

## Getting top guides

- **topLeading**: A guide that marks the top and leading edges of the view.
- **top**: A guide that marks the top edge of the view.
- **topTrailing**: A guide that marks the top and trailing edges of the view.

## Getting middle guides

- **leading**: A guide that marks the leading edge of the view.
- **center**: A guide that marks the center of the view.
- **trailing**: A guide that marks the trailing edge of the view.

## Getting bottom guides

- **bottomLeading**: A guide that marks the bottom and leading edges of the view.
- **bottom**: A guide that marks the bottom edge of the view.
- **bottomTrailing**: A guide that marks the bottom and trailing edges of the view.

## Getting text baseline guides

- **leadingFirstTextBaseline**: A guide that marks the leading edge and top-most text baseline in a view.
- **centerFirstTextBaseline**: A guide that marks the top-most text baseline in a view.
- **trailingFirstTextBaseline**: A guide that marks the trailing edge and top-most text baseline in a view.
- **leadingLastTextBaseline**: A guide that marks the leading edge and bottom-most text baseline in a view.
- **centerLastTextBaseline**: A guide that marks the bottom-most text baseline in a view.
- **trailingLastTextBaseline**: A guide that marks the trailing edge and bottom-most text baseline in a view.

## Creating a custom alignment

- **init(horizontal:vertical:)**: Creates a custom alignment value with the specified horizontal and vertical alignment guides.
- **horizontal**: The alignment on the horizontal axis.
- **vertical**: The alignment on the vertical axis.

## Aligning views

- **Aligning views within a stack**: Position views inside a stack using alignment guides.
- **Aligning views across stacks**: Create a custom alignment and use it to align views across multiple stacks.
- **alignmentGuide(_:computeValue:)**: Sets the view’s horizontal alignment.
- **HorizontalAlignment**: An alignment position along the horizontal axis.
- **VerticalAlignment**: An alignment position along the vertical axis.
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

