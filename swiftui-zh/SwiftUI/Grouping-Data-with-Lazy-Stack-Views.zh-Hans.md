--- 来源：https://developer.apple.com/documentation/SwiftUI/Grouping-Data-with-Lazy-Stack-Views

抓取时间：2025-12-02T17:38:06Z

---

# 使用惰性堆栈视图对数据进行分组

**Article**

在惰性堆栈视图中将内容拆分为逻辑部分。

## 概述

[LazyHStack](LazyHStack.zh-Hans.md) 和 [LazyVStack](LazyVStack.zh-Hans.md) 视图均能够显示按逻辑部分组织的视图组，分别以水平和垂直方向排列其子视图。这些堆栈之所以被称为“惰性”，是因为堆栈视图只有在需要渲染到屏幕上时才会创建项目。与堆栈视图一样，惰性堆栈视图本身不支持滚动，因此您应该将惰性堆栈视图包装在 [ScrollView](ScrollView.zh-Hans.md) 容器中。

要将内容或数据分组到惰性堆栈视图中，请使用 [Section](Section.zh-Hans.md) 实例作为分组视图集合的容器。[Section](Section.zh-Hans.md) 视图本身没有任何视觉表示，但可以包含页眉和页脚视图，这些视图可以随堆栈内容滚动，也可以固定到 [ScrollView](ScrollView.zh-Hans.md) 的顶部或底部。

本文中的代码示例构建了一个用于可视化原色色调的用户界面。堆栈中的每个部分代表一种原色，包含五个子视图，每个子视图显示该颜色的不同变体。

### 准备数据

与堆栈中包含的视图一样，每个 [Section](Section.zh-Hans.md) 在被 [ForEach](ForEach.zh-Hans.md) 迭代时必须具有唯一标识。在本例中，`ColorData` 实例代表各个部分，`ShadeData` 实例代表每个部分内每种颜色的色调。`ColorData` 和 `ShadeData` 均符合 [doc://com.apple.documentation/documentation/Swift/Identifiable] 协议。

```swift
struct ColorData: Identifiable {
    let id = UUID()
    let name: String
    let color: Color
    let variations: [ShadeData]

    struct ShadeData: Identifiable {
        let id = UUID()
        var brightness: Double
    }

    init(color: Color, name: String) {
        self.name = name
        self.color = color
        self.variations = stride(from: 0.0, to: 0.5, by: 0.1)
            .map { ShadeData(brightness: $0) }
    }
}
```

### 显示带页眉和页脚的部分

下面的 `ColorSelectionView` 设置了一个数组，其中包含每种原色的 `ColorData` 实例。[LazyVStack](LazyVStack.zh-Hans.md) 遍历颜色数据数组以创建部分，然后遍历 `variations` 以根据色调创建视图。

```swift
struct ColorSelectionView: View {
    let sections = [
        ColorData(color: .red, name: "Reds"),
        ColorData(color: .green, name: "Greens"),
        ColorData(color: .blue, name: "Blues")
    ]

    var body: some View {
        ScrollView {
            LazyVStack(spacing: 1) {
                ForEach(sections) { section in
                    Section(header: SectionHeaderView(colorData: section)) {
                        ForEach(section.variations) { variation in
                            section.color
                                .brightness(variation.brightness)
                                .frame(height: 20)
                        }
                    }
                }
            }
        }
    }
}
```

使用 [Section](Section.zh-Hans.md) 视图对数据进行分组，并传入带有 `header` 和 `footer` 属性的页眉或页脚视图。此示例使用 `SectionHeaderView` 作为页眉视图，其中包含一个半透明的堆栈视图，并在 [Text](Text.zh-Hans.md) 标签中显示该部分的颜色名称。

```swift
struct SectionHeaderView: View {
    var colorData: ColorData

    var body: some View {
        HStack {
            Text(colorData.name)
                .font(.headline)
                .foregroundColor(colorData.color)
            Spacer()
        }
        .padding()
        .background(Color.primary
                        .colorInvert()
                        .opacity(0.75))
    }
}
```

有关使用 [ForEach](ForEach.zh-Hans.md) 在堆栈中重复视图的更多信息，请参阅 [Creating-Performant-Scrollable-Stacks](Creating-Performant-Scrollable-Stacks.zh-Hans.md)。

### 保持重要信息可见

默认情况下，部分页眉和页脚视图将与部分内容同步滚动。如果您希望页眉和页脚视图始终保持可见，无论节的顶部或底部是否可见，请为惰性堆栈视图的 `pinnedViews` 属性指定一组 [PinnedScrollableViews](PinnedScrollableViews.zh-Hans.md)。

```swift
LazyVStack(spacing: 1, pinnedViews: [.sectionHeaders]) {
    // ...
}
```

在 [LazyVStack](LazyVStack.zh-Hans.md) 容器中，页眉固定在顶部，页脚固定在底部。在 [LazyHStack](LazyHStack.zh-Hans.md) 容器中，页眉固定在前缘，页脚固定在后缘。

通过此更改，当用户开始滚动时，节标题将固定在视图顶部。

## 动态排列一维视图

- **创建高性能可滚动堆栈**：使用滚动视图、堆栈视图和惰性堆栈高效地显示大量重复视图。

- **LazyHStack**：一种视图，其子元素以水平方向的行排列，仅在需要时创建元素。

- **LazyVStack**：一种视图，其子元素以垂直方向的行排列，仅在需要时创建元素。

- **PinnedScrollableViews**：一组可固定到滚动视图边界的视图类型。


---
source: https://developer.apple.com/documentation/SwiftUI/Grouping-Data-with-Lazy-Stack-Views
crawled: 2025-12-02T17:38:06Z
---

# Grouping data with lazy stack views

**Article**

Split content into logical sections inside lazy stack views.

## Overview

[LazyHStack](LazyHStack.zh-Hans.md) and [LazyVStack](LazyVStack.zh-Hans.md) views are both able to display groups of views organized into logical sections, arranging their children in lines that grow horizontally and vertically, respectively. These stacks are “lazy” in that the stack views don’t create items until they need to be rendered onscreen. Like stack views, lazy stacks don’t include any inherent support for scrolling, and you should wrap lazy stack views in [ScrollView](ScrollView.zh-Hans.md) containers.

To group content or data inside a lazy stack view, use [Section](Section.zh-Hans.md) instances as containers for collections of grouped views. [Section](Section.zh-Hans.md) views don’t have any visual representation themselves but can contain header and footer views that can either scroll with the stack’s content or that you can pin to the top or bottom of the [ScrollView](ScrollView.zh-Hans.md).



The code samples in this article build a user interface for visualizing shades of primary colors. Each section in the stack represents a primary color, containing five subviews, each showing a different variation of the color.



### Prepare your data

As with views contained within a stack, each [Section](Section.zh-Hans.md) must be uniquely identifiable when iterated by [ForEach](ForEach.zh-Hans.md). In this example, `ColorData` instances represent the sections, and `ShadeData` instances represent the shades of each color inside a section. Both `ColorData` and `ShadeData` conform to the [doc://com.apple.documentation/documentation/Swift/Identifiable] protocol.

```swift
struct ColorData: Identifiable {
    let id = UUID()
    let name: String
    let color: Color
    let variations: [ShadeData]

    struct ShadeData: Identifiable {
        let id = UUID()
        var brightness: Double
    }

    init(color: Color, name: String) {
        self.name = name
        self.color = color
        self.variations = stride(from: 0.0, to: 0.5, by: 0.1)
            .map { ShadeData(brightness: $0) }
    }
}
```

### Display sections with headers and footers

The `ColorSelectionView` below sets up an array containing `ColorData` instances for each primary color. The [LazyVStack](LazyVStack.zh-Hans.md) iterates over the array of color data to create sections, then iterates over the `variations` to create views from the shades.

```swift
struct ColorSelectionView: View {
    let sections = [
        ColorData(color: .red, name: "Reds"),
        ColorData(color: .green, name: "Greens"),
        ColorData(color: .blue, name: "Blues")
    ]

    var body: some View {
        ScrollView {
            LazyVStack(spacing: 1) {
                ForEach(sections) { section in
                    Section(header: SectionHeaderView(colorData: section)) {
                        ForEach(section.variations) { variation in
                            section.color
                                .brightness(variation.brightness)
                                .frame(height: 20)
                        }
                    }
                }
            }
        }
    }
}
```

Group data with [Section](Section.zh-Hans.md) views and pass in a header or footer view with the `header` and `footer` properties. This example implements a `SectionHeaderView` as a header view, containing a semi-transparent stack view and the name of the section’s color in a [Text](Text.zh-Hans.md) label.

```swift
struct SectionHeaderView: View {
    var colorData: ColorData

    var body: some View {
        HStack {
            Text(colorData.name)
                .font(.headline)
                .foregroundColor(colorData.color)
            Spacer()
        }
        .padding()
        .background(Color.primary
                        .colorInvert()
                        .opacity(0.75))
    }
}
```

For more information on using [ForEach](ForEach.zh-Hans.md) to repeat views inside a stack, see [Creating-Performant-Scrollable-Stacks](Creating-Performant-Scrollable-Stacks.zh-Hans.md).

### Keep important information visible

By default, section header and footer views will scroll in sync with section content. If you want header and footer views to always remain visible, regardless of whether the top or bottom of the section is visible, then specify a set of [PinnedScrollableViews](PinnedScrollableViews.zh-Hans.md) for the `pinnedViews` property of the lazy stack view.

```swift
LazyVStack(spacing: 1, pinnedViews: [.sectionHeaders]) {
    // ...
}
```

In [LazyVStack](LazyVStack.zh-Hans.md) containers, headers attach to the top and footers to the bottom. In [LazyHStack](LazyHStack.zh-Hans.md) containers, headers attach to the leading edge and footers to the trailing edge.

With this change, section headers are pinned to the top of the view as the user begins to scroll.



## Dynamically arranging views in one dimension

- **Creating performant scrollable stacks**: Display large numbers of repeated views efficiently with scroll views, stack views, and lazy stacks.
- **LazyHStack**: A view that arranges its children in a line that grows horizontally, creating items only as needed.
- **LazyVStack**: A view that arranges its children in a line that grows vertically, creating items only as needed.
- **PinnedScrollableViews**: A set of view types that may be pinned to the bounds of a scroll view.

