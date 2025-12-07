---
来源： https://developer.apple.com/documentation/SwiftUI/Aligning-Views-Across-Stacks
抓取时间： 2025-12-02T17:38:46Z
---

# 跨堆栈对齐视图

**Article**

创建自定义对齐方式，并用于跨多个堆栈对齐视图。

## 概览

当你将堆栈嵌套在一起时，你可能希望堆栈中的特定项目彼此对齐。默认情况下，为堆栈指定的对齐方式仅适用于该堆栈的子视图。要对齐嵌套堆栈中的子视图，可定义自定义对齐方式，将其分配给外层视图，并使用对齐方式引导修改器来确定要对齐的特定视图。

###从默认居中对齐方式开始

为了说明跨堆栈对齐项目的情况，下面的视图显示了一个水平堆栈包裹着两个嵌套的垂直堆栈，这两个堆栈的子视图数量不同。包围的 [HStack](HStack.zh-Hans.md) 没有定义对齐方式，因此默认为 [center](VerticalAlignment/center.zh-Hans.md)。

```swift
struct ImageRow: View {
    var body: some View {
        HStack {
            VStack {
                Image("bell_peppers")
                    .resizable()
                    .scaledToFit()
                Text("Bell Peppers")
                    .font(.title)
            }
            VStack {
                Image("chili_peppers")
                    .resizable()
                    .scaledToFit()
                Text("Chili Peppers")
                    .font(.title)
                Text("Higher levels of capsicum")
                    .font(.caption)
            }
        }
    }
}
```

下图显示了嵌套垂直堆栈的内容，这些内容在堆栈中心对齐。垂直堆栈中的子元素，如每张图片下方的标题，并不互相对齐。



###定义自定义对齐方式

要创建新的垂直排列向导，请扩展[VerticalAlignment](VerticalAlignment.zh-Hans.md)，为向导添加新的静态属性。根据对齐方式命名该向导，使其更易于使用。下面的示例将底部定位作为该向导的默认值：

```swift
extension VerticalAlignment {
    /// A custom alignment for image titles.
    private struct ImageTitleAlignment: AlignmentID {
        static func defaultValue(in context: ViewDimensions) -> CGFloat {
            // Default to bottom alignment if no guides are set.
            context[VerticalAlignment.bottom]
        }
    }

    /// A guide for aligning titles.
    static let imageTitleAlignmentGuide = VerticalAlignment(
        ImageTitleAlignment.self
    )
}
```

###指定并应用自定义对齐方式

要使用对齐方式向导，请将其分配给包含要对齐的视图的父视图。下面的示例指定`imageTitleAlignmentGuide` 作为水平堆叠的对齐方式：

```swift
struct RowOfAlignedImages: View {
    var body: some View {
        HStack(alignment: .imageTitleAlignmentGuide) {
            VStack {
                Image("bell_peppers")
                    .resizable()
                    .scaledToFit()

                Text("Bell Peppers")
                    .font(.title)
            }
            VStack {
                Image("chili_peppers")
                    .resizable()
                    .scaledToFit()

                Text("Chili Peppers")
                    .font(.title)

                Text("Higher levels of capsicum")
                    .font(.caption)
            }
        }
    }
}
```

现在，两个垂直堆叠对齐在堆叠底部，使用自定义向导规范中的默认值。



在堆栈上定义对齐方式后，它将通过所包围的子视图进行投影。在嵌套的[VStack](VStack.zh-Hans.md) 实例中，使用[alignmentGuide(_:computeValue:)](View/alignmentGuide___computeValue.zh-Hans.md) 的自定义向导，将[HStack](HStack.zh-Hans.md) 应用于要对齐的视图。

```swift
struct RowOfAlignedImages: View {
    var body: some View {
        HStack(alignment: .imageTitleAlignmentGuide) {
            VStack {
                Image("bell_peppers")
                    .resizable()
                    .scaledToFit()

                Text("Bell Peppers")
                    .font(.title)
                    .alignmentGuide(.imageTitleAlignmentGuide) { context in
                        context[.firstTextBaseline]
                    }
            }
            VStack {
                Image("chili_peppers")
                    .resizable()
                    .scaledToFit()

                Text("Chili Peppers")
                    .font(.title)
                    .alignmentGuide(.imageTitleAlignmentGuide) { context in
                        context[.firstTextBaseline]
                    }

                Text("Higher levels of capsicum")
                    .font(.caption)
            }
        }
    }
}
```

对齐引导修改器的闭包返回 [firstTextBaseline](VerticalAlignment/firstTextBaseline.zh-Hans.md)，使标题的基线与对齐引导 `imageTitleAlignmentGuide`对齐。



## 对齐视图

- 在堆栈内对齐视图**：使用对齐指引在堆栈内定位视图。
- **alignmentGuide(_:computeValue:)**：设置视图的水平对齐方式。
- **Alignment**：设置视图的水平对齐方式：双轴对齐。
- **HorizontalAlignment**：沿水平轴的对齐位置。
- **VerticalAlignment**： 沿垂直轴对齐的位置：沿垂直轴对齐的位置。
- **DepthAlignment**： 沿深度轴的对齐位置：沿深度轴的对齐位置。
- **AlignmentID**：用于创建自定义对齐导轨的类型。
- **ViewDimensions**：视图在其自身坐标空间中的尺寸和对齐方式向导。
- **ViewDimensions3D**：视图在其自身坐标空间中的三维尺寸和对齐向导。
- **SpatialContainer**：在三维空间中对齐重叠内容的布局容器。


---
source: https://developer.apple.com/documentation/SwiftUI/Aligning-Views-Across-Stacks
crawled: 2025-12-02T17:38:46Z
---

# Aligning views across stacks

**Article**

Create a custom alignment and use it to align views across multiple stacks.

## Overview

As you nest stacks together, you may want specific items within those stacks to align with each other. By default, the alignment you specify for a stack applies only to that stack’s child views. To align child views that reside in the nested stacks, define a custom alignment, assign it to the enclosing view, and use the alignment guide modifier to identify specific views to align.

### Begin with the default center alignment

To illustrate aligning items across stacks, the following view shows a horizontal stack wrapping around two nested vertical stacks that have a different number of child views. The enclosing [HStack](HStack.zh-Hans.md) doesn’t define an alignment, so it defaults to [center](VerticalAlignment/center.zh-Hans.md).

```swift
struct ImageRow: View {
    var body: some View {
        HStack {
            VStack {
                Image("bell_peppers")
                    .resizable()
                    .scaledToFit()
                Text("Bell Peppers")
                    .font(.title)
            }
            VStack {
                Image("chili_peppers")
                    .resizable()
                    .scaledToFit()
                Text("Chili Peppers")
                    .font(.title)
                Text("Higher levels of capsicum")
                    .font(.caption)
            }
        }
    }
}
```

The image below shows the contents of a nested vertical stack aligning at the center of the stack. The child elements within the vertical stacks, such as the titles beneath each image, don’t align with each other.



### Define a custom alignment

To create a new vertical alignment guide, extend [VerticalAlignment](VerticalAlignment.zh-Hans.md) with a new static property for your guide. Name the guide according to what it aligns to make it easier to use. The following example uses bottom positioning as the default value for this guide:

```swift
extension VerticalAlignment {
    /// A custom alignment for image titles.
    private struct ImageTitleAlignment: AlignmentID {
        static func defaultValue(in context: ViewDimensions) -> CGFloat {
            // Default to bottom alignment if no guides are set.
            context[VerticalAlignment.bottom]
        }
    }

    /// A guide for aligning titles.
    static let imageTitleAlignmentGuide = VerticalAlignment(
        ImageTitleAlignment.self
    )
}
```

### Assign and apply the custom alignment

To use the alignment guide, assign it to a parent view that encloses the views you want to align. The following example specifies `imageTitleAlignmentGuide` as the alignment for the horizontal stack:

```swift
struct RowOfAlignedImages: View {
    var body: some View {
        HStack(alignment: .imageTitleAlignmentGuide) {
            VStack {
                Image("bell_peppers")
                    .resizable()
                    .scaledToFit()

                Text("Bell Peppers")
                    .font(.title)
            }
            VStack {
                Image("chili_peppers")
                    .resizable()
                    .scaledToFit()

                Text("Chili Peppers")
                    .font(.title)

                Text("Higher levels of capsicum")
                    .font(.caption)
            }
        }
    }
}
```

The two vertical stacks now align on the bottoms of the stacks, using the default from your specification for the custom guide.



When you define an alignment on a stack, it projects through enclosed child views. Within the nested [VStack](VStack.zh-Hans.md) instances, apply [alignmentGuide(_:computeValue:)](View/alignmentGuide___computeValue.zh-Hans.md) to the views to align, using your custom guide for the [HStack](HStack.zh-Hans.md).

```swift
struct RowOfAlignedImages: View {
    var body: some View {
        HStack(alignment: .imageTitleAlignmentGuide) {
            VStack {
                Image("bell_peppers")
                    .resizable()
                    .scaledToFit()

                Text("Bell Peppers")
                    .font(.title)
                    .alignmentGuide(.imageTitleAlignmentGuide) { context in
                        context[.firstTextBaseline]
                    }
            }
            VStack {
                Image("chili_peppers")
                    .resizable()
                    .scaledToFit()

                Text("Chili Peppers")
                    .font(.title)
                    .alignmentGuide(.imageTitleAlignmentGuide) { context in
                        context[.firstTextBaseline]
                    }

                Text("Higher levels of capsicum")
                    .font(.caption)
            }
        }
    }
}
```

The closure from the alignment guide modifier returns [firstTextBaseline](VerticalAlignment/firstTextBaseline.zh-Hans.md), which aligns the baselines of the titles with the alignment guide `imageTitleAlignmentGuide`.



## Aligning views

- **Aligning views within a stack**: Position views inside a stack using alignment guides.
- **alignmentGuide(_:computeValue:)**: Sets the view’s horizontal alignment.
- **Alignment**: An alignment in both axes.
- **HorizontalAlignment**: An alignment position along the horizontal axis.
- **VerticalAlignment**: An alignment position along the vertical axis.
- **DepthAlignment**: An alignment position along the depth axis.
- **AlignmentID**: A type that you use to create custom alignment guides.
- **ViewDimensions**: A view’s size and alignment guides in its own coordinate space.
- **ViewDimensions3D**: A view’s 3D size and alignment guides in its own coordinate space.
- **SpatialContainer**: A layout container that aligns overlapping content in 3D space.

