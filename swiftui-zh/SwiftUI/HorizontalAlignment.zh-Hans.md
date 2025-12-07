---
来源： https://developer.apple.com/documentation/SwiftUI/HorizontalAlignment
抓取时间： 2025-12-02T17:38:48Z
---

# 水平对齐方式

**Structure**

沿水平轴的对齐位置。

## 声明

```swift
@frozen struct HorizontalAlignment
```

## 概览

使用水平对齐向导可告诉 SwiftUI 如何水平相对定位视图，就像在 [VStack](VStack.zh-Hans.md) 中垂直放置视图一样。下面的示例演示了常见的内置水平对齐方式：



您可以通过创建一系列以垂直堆栈形式实现的列来生成上述示例，并为每个堆栈配置不同的对齐方式：

```swift
private struct HorizontalAlignmentGallery: View {
    var body: some View {
        HStack(spacing: 30) {
            column(alignment: .leading, text: "Leading")
            column(alignment: .center, text: "Center")
            column(alignment: .trailing, text: "Trailing")
        }
        .frame(height: 150)
    }

    private func column(alignment: HorizontalAlignment, text: String) -> some View {
        VStack(alignment: alignment, spacing: 0) {
            Color.red.frame(width: 1)
            Text(text).font(.title).border(.gray)
            Color.red.frame(width: 1)
        }
    }
}
```

在布局过程中，SwiftUI 通过汇集受影响视图的指定向导来对齐每个堆栈内的视图。SwiftUI 会根据特定视图的特征计算该视图的导轨位置。例如，[center](HorizontalAlignment/center.zh-Hans.md) 导向符显示在视图宽度的一半处。您可以使用[alignmentGuide(_:computeValue:)](View/alignmentGuide___computeValue.zh-Hans.md) 视图修改器覆盖特定视图的导引计算。

### 布局方向

当用户将其设备配置为使用从左到右的语言（如英语）时，系统会将前导对齐方式放在左边，而将后导对齐方式放在右边，如上一节的示例所示。但是，在从右到左的语言中，系统会将其颠倒过来。使用[environment(_:_:)](View/environment.zh-Hans.md)视图修饰符显式覆盖上面定义的视图的[layoutDirection](EnvironmentValues/layoutDirection.zh-Hans.md)环境值，就可以看到这一点：

```swift
HorizontalAlignmentGallery()
    .environment(\.layoutDirection, .rightToLeft)
```



这种自动布局调整使本地化应用程序变得更容易，但仍需针对不同的本地语言测试应用程序。有关本地化过程的更多信息，请参阅 [doc://com.apple.documentation/documentation/Xcode/localization]。

### 自定义对齐指南

您可以创建符合 [AlignmentID](AlignmentID.zh-Hans.md) 协议的类型，然后使用该类型在 `HorizontalAlignment` 上初始化一个新的静态属性，从而创建自定义水平对齐方式：

```swift
private struct OneQuarterAlignment: AlignmentID {
    static func defaultValue(in context: ViewDimensions) -> CGFloat {
        context.width / 4
    }
}

extension HorizontalAlignment {
    static let oneQuarter = HorizontalAlignment(OneQuarterAlignment.self)
}
```

执行[defaultValue(in:)](AlignmentID/defaultValue_in.zh-Hans.md) 方法可计算自定义对齐方式向导的默认值。该方法接收[ViewDimensions](ViewDimensions.zh-Hans.md) 实例，您可以使用该实例根据视图的特征计算出适当的值。上面的示例将对齐导向器放置在视图宽度的四分之一处，从视图的原点开始测量。

然后，您就可以像使用任何内置导轨一样使用自定义对齐导轨。例如，您可以将其作为`alignment`参数用于[VStack](VStack.zh-Hans.md)，也可以使用[alignmentGuide(_:computeValue:)](View/alignmentGuide___computeValue.zh-Hans.md)视图修改器为特定视图更改它。自定义对齐向导也会像内置向导一样，在从右到左的环境中自动反转。

### 复合对齐方式

将[VerticalAlignment](VerticalAlignment.zh-Hans.md) 与`HorizontalAlignment` 结合使用，可创建一个复合[Alignment](Alignment.zh-Hans.md)，在一个值中同时表示垂直和水平定位。例如，您可以将上一节中自定义的`oneQuarter` 水平对齐方式与内置的[center](VerticalAlignment/center.zh-Hans.md) 垂直对齐方式结合起来，在[ZStack](ZStack.zh-Hans.md) 中使用：

```swift
struct LayeredVerticalStripes: View {
    var body: some View {
        ZStack(alignment: Alignment(horizontal: .oneQuarter, vertical: .center)) {
            verticalStripes(color: .blue)
                .frame(width: 300, height: 150)
            verticalStripes(color: .green)
                .frame(width: 180, height: 80)
        }
    }

    private func verticalStripes(color: Color) -> some View {
        HStack(spacing: 1) {
            ForEach(0..<4) { _ in color }
        }
    }
}
```

上面的示例使用的宽度和高度产生了两组不匹配的四条垂直条纹。[ZStack](ZStack.zh-Hans.md)将两组条纹垂直居中，并在水平方向上将它们对齐，距离每组条纹的前缘四分之一处。在从左到右的位置中，这对齐了每组最左边条纹的右边缘：



## 获取指南

- **leading**：标记视图前缘的向导。
- **center**：标记视图水平中心的导标。
- **trailing**：标记视图尾部边缘的导轨。
- **listRowSeparatorLeading**：`List`行分隔线前缘的标记。
- **listRowSeparatorTrailing**：标记`List`行分隔线后缘的导轨。

## 创建自定义对齐方式

- **init(_:)**：创建指定类型的自定义水平对齐方式。
- **combineExplicit(_:)**：合并此实例生成的显式对齐值序列。

## 对齐视图

- 在堆栈内对齐视图**：使用排列向导在堆栈内定位视图。
- 跨堆栈对齐视图**：创建自定义对齐方式，并使用它在多个堆栈中对齐视图。
- **alignmentGuide(_:computeValue:)**：设置视图的水平对齐方式。
- **Alignment**：设置视图的水平对齐方式：双轴对齐。
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
source: https://developer.apple.com/documentation/SwiftUI/HorizontalAlignment
crawled: 2025-12-02T17:38:48Z
---

# HorizontalAlignment

**Structure**

An alignment position along the horizontal axis.

## Declaration

```swift
@frozen struct HorizontalAlignment
```

## Overview

Use horizontal alignment guides to tell SwiftUI how to position views relative to one another horizontally, like when you place views vertically in an [VStack](VStack.zh-Hans.md). The following example demonstrates common built-in horizontal alignments:



You can generate the example above by creating a series of columns implemented as vertical stacks, where you configure each stack with a different alignment guide:

```swift
private struct HorizontalAlignmentGallery: View {
    var body: some View {
        HStack(spacing: 30) {
            column(alignment: .leading, text: "Leading")
            column(alignment: .center, text: "Center")
            column(alignment: .trailing, text: "Trailing")
        }
        .frame(height: 150)
    }

    private func column(alignment: HorizontalAlignment, text: String) -> some View {
        VStack(alignment: alignment, spacing: 0) {
            Color.red.frame(width: 1)
            Text(text).font(.title).border(.gray)
            Color.red.frame(width: 1)
        }
    }
}
```

During layout, SwiftUI aligns the views inside each stack by bringing together the specified guides of the affected views. SwiftUI calculates the position of a guide for a particular view based on the characteristics of the view. For example, the [center](HorizontalAlignment/center.zh-Hans.md) guide appears at half the width of the view. You can override the guide calculation for a particular view using the [alignmentGuide(_:computeValue:)](View/alignmentGuide___computeValue.zh-Hans.md) view modifier.

### Layout direction

When a user configures their device to use a left-to-right language like English, the system places the leading alignment on the left and the trailing alignment on the right, as the example from the previous section demonstrates. However, in a right-to-left language, the system reverses these. You can see this by using the [environment(_:_:)](View/environment.zh-Hans.md) view modifier to explicitly override the [layoutDirection](EnvironmentValues/layoutDirection.zh-Hans.md) environment value for the view defined above:

```swift
HorizontalAlignmentGallery()
    .environment(\.layoutDirection, .rightToLeft)
```



This automatic layout adjustment makes it easier to localize your app, but it’s still important to test your app for the different locales that you ship into. For more information about the localization process, see [doc://com.apple.documentation/documentation/Xcode/localization].

### Custom alignment guides

You can create a custom horizontal alignment by creating a type that conforms to the [AlignmentID](AlignmentID.zh-Hans.md) protocol, and then using that type to initialize a new static property on `HorizontalAlignment`:

```swift
private struct OneQuarterAlignment: AlignmentID {
    static func defaultValue(in context: ViewDimensions) -> CGFloat {
        context.width / 4
    }
}

extension HorizontalAlignment {
    static let oneQuarter = HorizontalAlignment(OneQuarterAlignment.self)
}
```

You implement the [defaultValue(in:)](AlignmentID/defaultValue_in.zh-Hans.md) method to calculate a default value for the custom alignment guide. The method receives a [ViewDimensions](ViewDimensions.zh-Hans.md) instance that you can use to calculate an appropriate value based on characteristics of the view. The example above places the guide at one quarter of the width of the view, as measured from the view’s origin.

You can then use the custom alignment guide like any built-in guide. For example, you can use it as the `alignment` parameter to a [VStack](VStack.zh-Hans.md), or you can change it for a specific view using the [alignmentGuide(_:computeValue:)](View/alignmentGuide___computeValue.zh-Hans.md) view modifier. Custom alignment guides also automatically reverse in a right-to-left environment, just like built-in guides.

### Composite alignment

Combine a [VerticalAlignment](VerticalAlignment.zh-Hans.md) with a `HorizontalAlignment` to create a composite [Alignment](Alignment.zh-Hans.md) that indicates both vertical and horizontal positioning in one value. For example, you could combine your custom `oneQuarter` horizontal alignment from the previous section with a built-in [center](VerticalAlignment/center.zh-Hans.md) vertical alignment to use in a [ZStack](ZStack.zh-Hans.md):

```swift
struct LayeredVerticalStripes: View {
    var body: some View {
        ZStack(alignment: Alignment(horizontal: .oneQuarter, vertical: .center)) {
            verticalStripes(color: .blue)
                .frame(width: 300, height: 150)
            verticalStripes(color: .green)
                .frame(width: 180, height: 80)
        }
    }

    private func verticalStripes(color: Color) -> some View {
        HStack(spacing: 1) {
            ForEach(0..<4) { _ in color }
        }
    }
}
```

The example above uses widths and heights that generate two mismatched sets of four vertical stripes. The [ZStack](ZStack.zh-Hans.md) centers the two sets vertically and aligns them horizontally one quarter of the way from the leading edge of each set. In a left-to-right locale, this aligns the right edges of the left-most stripes of each set:



## Getting guides

- **leading**: A guide that marks the leading edge of the view.
- **center**: A guide that marks the horizontal center of the view.
- **trailing**: A guide that marks the trailing edge of the view.
- **listRowSeparatorLeading**: A guide marking the leading edge of a `List` row separator.
- **listRowSeparatorTrailing**: A guide marking the trailing edge of a `List` row separator.

## Creating a custom alignment

- **init(_:)**: Creates a custom horizontal alignment of the specified type.
- **combineExplicit(_:)**: Merges a sequence of explicit alignment values produced by this instance.

## Aligning views

- **Aligning views within a stack**: Position views inside a stack using alignment guides.
- **Aligning views across stacks**: Create a custom alignment and use it to align views across multiple stacks.
- **alignmentGuide(_:computeValue:)**: Sets the view’s horizontal alignment.
- **Alignment**: An alignment in both axes.
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

