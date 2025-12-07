--- 来源：https://developer.apple.com/documentation/SwiftUI/Picking-Container-Views-for-Your-Content

抓取时间：2025-12-02T17:38:04Z

---

# 为您的内容选择容器视图

**Article**

使用堆栈、网格、列表和表单构建灵活的用户界面。

## 概述

SwiftUI 提供了一系列容器视图，用于对视图进行分组和重复。某些容器视图纯粹用于结构和布局，例如堆栈视图、惰性堆栈视图和网格视图。而其他容器视图，例如列表和表单，则用于实现系统标准的视觉效果和交互方式。

为应用程序用户界面的每个部分选择最合适的容器视图是一项重要的技能；它可以帮助您完成各种任务，从将两个视图并排放置，到创建包含数百个元素的复杂布局。

### 视图集合分组

堆栈视图是 SwiftUI 中最基本的布局容器。使用堆栈视图可以将视图集合分组到水平或垂直行中，或者将它们堆叠在一起。

使用 [HStack](HStack.zh-Hans.md) 将视图排列成水平行，使用 [VStack](VStack.zh-Hans.md) 将视图排列成垂直行，使用 [ZStack](ZStack.zh-Hans.md) 将视图层叠在一起。然后，组合堆栈视图来构建更复杂的布局。这三种堆栈视图，以及它们的对齐和间距属性、视图修饰符和 [Spacer](Spacer.zh-Hans.md) 视图，共同提供了极大的布局灵活性。

您经常将堆栈视图用作其他容器视图中的构建块。例如，一个 [List](List.zh-Hans.md) 通常包含堆栈视图，您可以使用它们在每一行中布局视图。

有关使用堆栈视图布局视图的更多信息，请参阅 [Building-Layouts-with-Stack-Views](Building-Layouts-with-Stack-Views.zh-Hans.md)。

### 重复视图或视图组

您还可以使用 [HStack](HStack.zh-Hans.md)、[VStack](VStack.zh-Hans.md)、[LazyHStack](LazyHStack.zh-Hans.md) 和 [LazyVStack](LazyVStack.zh-Hans.md) 来重复视图或视图组。将堆栈视图放置在 [ScrollView](ScrollView.zh-Hans.md) 内，以便内容可以扩展到容器边界之外。用户可以同时水平、垂直或双向滚动。

堆栈视图和延迟加载堆栈视图的功能类似，它们可能看起来可以互换，但它们在不同的情况下各有优势。堆栈视图一次性加载所有子视图，使布局快速可靠，因为系统在加载每个子视图时就知道它们的大小和形状。惰性堆栈会牺牲一定程度的布局正确性来换取性能提升，因为系统只会在子视图可见时才计算其几何形状。

选择堆栈视图类型时，始终先使用标准堆栈视图，只有当代码分析显示惰性堆栈视图能带来显著的性能提升时，才切换到惰性堆栈视图。有关惰性堆栈视图以及如何衡量应用程序视图加载性能的更多信息，请参阅 [Creating-Performant-Scrollable-Stacks](Creating-Performant-Scrollable-Stacks.zh-Hans.md)。

### 在二维布局中定位视图

要同时水平和垂直布局视图，请使用 [LazyVGrid](LazyVGrid.zh-Hans.md) 或 [LazyHGrid](LazyHGrid.zh-Hans.md)。网格是布局自然以方形容器显示的内容（例如图片库）的理想容器选择。网格也是将用户界面布局放大以在大尺寸设备上显示的理想选择。例如，联系人信息目录在 iPhone 上可能适合列表或垂直堆叠布局，但在 iPad 或 Mac 等更大设备上放大显示时，网格布局可能更合适。

与堆叠视图类似，SwiftUI 网格视图本身并不包含滚动视口；如果内容可能超出可用空间，请将其放置在 [ScrollView](ScrollView.zh-Hans.md) 中。

### 显示数据集合并与之交互

SwiftUI 中的 [List](List.zh-Hans.md) 视图在概念上类似于 [LazyVStack](LazyVStack.zh-Hans.md) 和 [ScrollView](ScrollView.zh-Hans.md) 的组合，但默认情况下，它会在其包含的项目周围和之间应用平台相关的视觉样式。例如，在 iOS 上运行时，[List](List.zh-Hans.md) 的默认配置会在行之间添加分隔线，并为带有导航的项绘制展开指示器，前提是该列表包含在 [NavigationView](NavigationView.zh-Hans.md) 中。

[List](List.zh-Hans.md) 视图还支持平台相关的交互功能，例如插入、重新排序和删除项目等常见操作。例如，在 [List](List.zh-Hans.md) 内的 [ForEach](ForEach.zh-Hans.md) 中添加 [onDelete(perform:)](DynamicViewContent/onDelete_perform.zh-Hans.md) 修饰符，即可启用系统标准的滑动删除交互功能。

与 [LazyHStack](LazyHStack.zh-Hans.md) 和 [LazyVStack](LazyVStack.zh-Hans.md) 类似，SwiftUI [List](List.zh-Hans.md) 内的行也采用延迟加载，并且没有非延迟加载的对应版本。列表本身会在必要时自动滚动，无需将其包裹在 [ScrollView](ScrollView.zh-Hans.md) 中。

### 数据输入的分组视图和控件

使用 [Form](Form.zh-Hans.md) 构建使用系统标准控件的数据输入界面、设置或偏好设置屏幕。

与所有 SwiftUI 视图一样，表单会以平台适用的方式显示其内容。请注意，[Form](Form.zh-Hans.md) 内的控件布局可能因平台而异。例如，在 iOS 上，[Form](Form.zh-Hans.md) 中的 [Picker](Picker.zh-Hans.md) 控件会添加导航，在单独的屏幕上显示选择器的选项；而在 macOS 上，同样的 [Picker](Picker.zh-Hans.md) 控件则会显示一个弹出按钮或一组单选按钮。


---
source: https://developer.apple.com/documentation/SwiftUI/Picking-Container-Views-for-Your-Content
crawled: 2025-12-02T17:38:04Z
---

# Picking container views for your content

**Article**

Build flexible user interfaces by using stacks, grids, lists, and forms.

## Overview

SwiftUI provides a range of container views that group and repeat views. Use some containers purely for structure and layout, like stack views, lazy stack views, and grid views. Use others, like lists and forms, to also adopt system-standard visuals and interactivity.

Choosing the most appropriate container views for each part of your app’s user interface is an important skill to learn; it helps you with everything from positioning two views next to each other, to creating complex layouts with hundreds of elements.

### Group collections of views

Stack views are the most primitive layout container available in SwiftUI. Use stacks to group collections of views into horizontal or vertical lines, or to stack them on top of one another.

Use [HStack](HStack.zh-Hans.md) to lay out views in a horizontal line, [VStack](VStack.zh-Hans.md) to position views in a vertical line, and [ZStack](ZStack.zh-Hans.md) to layer views on top of one another. Then, combine stack views to compose more complex layouts. These three kinds of stacks, along with their alignment and spacing properties, view modifiers, and [Spacer](Spacer.zh-Hans.md) views combine to allow extensive layout flexibility.



You often use stack views as building blocks inside other container views. For example, a [List](List.zh-Hans.md) typically contains stack views, with which you lay out views inside each row.

For more information on using stack views to lay out views, see [Building-Layouts-with-Stack-Views](Building-Layouts-with-Stack-Views.zh-Hans.md).

### Repeat views or groups of views

You can also use [HStack](HStack.zh-Hans.md), [VStack](VStack.zh-Hans.md), [LazyHStack](LazyHStack.zh-Hans.md), and [LazyVStack](LazyVStack.zh-Hans.md) to repeat views or groups of views. Place a stack view inside a [ScrollView](ScrollView.zh-Hans.md) so your content can expand beyond the bounds of its container. Users can simultaneously scroll horizontally, vertically, or in both directions.

Stack views and lazy stacks have similar functionality, and they may feel interchangeable, but they each have strengths in different situations. Stack views load their child views all at once, making layout fast and reliable, because the system knows the size and shape of every subview as it loads them. Lazy stacks trade some degree of layout correctness for performance, because the system only calculates the geometry for subviews as they become visible.



When choosing the type of stack view to use, always start with a standard stack view and only switch to a lazy stack if profiling your code shows a worthwhile performance improvement. For more information on lazy stack views and how to measure your app’s view loading performance, see [Creating-Performant-Scrollable-Stacks](Creating-Performant-Scrollable-Stacks.zh-Hans.md).

### Position views in a two-dimensional layout

To lay out views horizontally and vertically at the same time, use a [LazyVGrid](LazyVGrid.zh-Hans.md) or [LazyHGrid](LazyHGrid.zh-Hans.md). Grids are a good container choice to lay out content that naturally displays in square containers, like an image gallery. Grids are also a good choice to scale user interface layouts up for display on larger devices. For example, a directory of contact information might suit a list or vertical stack on an iPhone, but might fit more naturally in a grid layout when scaled up to a larger device like the iPad or Mac.



Like stack views, SwiftUI grid views don’t inherently include a scrolling viewport; place them inside a [ScrollView](ScrollView.zh-Hans.md) if the content might be larger than the available space.

### Display and interact with collections of data

[List](List.zh-Hans.md) views in SwiftUI are conceptually similar to the combination of a [LazyVStack](LazyVStack.zh-Hans.md) and [ScrollView](ScrollView.zh-Hans.md), but by default will include platform-appropriate visual styling around and between their contained items. For example, when running on iOS, the default configuration of a [List](List.zh-Hans.md) adds separator lines between rows, and draws disclosure indicators for items which have navigation, and where the list is contained in a [NavigationView](NavigationView.zh-Hans.md).

[List](List.zh-Hans.md) views also support platform-appropriate interactivity for common tasks such as inserting, reordering, and removing items. For example, adding the [onDelete(perform:)](DynamicViewContent/onDelete_perform.zh-Hans.md) modifier to a [ForEach](ForEach.zh-Hans.md) inside a [List](List.zh-Hans.md) will enable system-standard swipe-to-delete interactivity.

Like [LazyHStack](LazyHStack.zh-Hans.md) and [LazyVStack](LazyVStack.zh-Hans.md), rows inside a SwiftUI [List](List.zh-Hans.md) also load lazily, and there is no non-lazy equivalent. Lists inherently scroll when necessary, and you don’t need to wrap them in a [ScrollView](ScrollView.zh-Hans.md).

### Group views and controls for data entry

Use [Form](Form.zh-Hans.md) to build data-entry interfaces, settings, or preference screens that use system-standard controls.



Like all SwiftUI views, forms display their content in a platform-appropriate way. Be aware that the layout of controls inside a [Form](Form.zh-Hans.md) may differ significantly based on the platform. For example, a [Picker](Picker.zh-Hans.md) control in a [Form](Form.zh-Hans.md) on iOS adds navigation, showing the picker’s choices on a separate screen, while the same [Picker](Picker.zh-Hans.md) on macOS displays a pop-up button or set of radio buttons.

