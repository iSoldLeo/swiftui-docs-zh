---
来源： https://developer.apple.com/documentation/SwiftUI/Creating-Performant-Scrollable-Stacks
抓取时间： 2025-12-02T17:38:07Z
---

# 创建性能良好的可滚动堆栈

**Article**

使用滚动视图、堆栈视图和懒堆栈高效显示大量重复视图。

### 概览

您的应用程序经常需要在容器视图中显示比设备屏幕空间更多的数据。水平和垂直堆栈是重复视图或视图组的良好解决方案，但它们没有内置的滚动机制。你可以通过将堆栈包裹在[ScrollView](ScrollView.zh-Hans.md)内来添加滚动功能，并在出现性能问题时切换到懒堆栈。

### 在可滚动容器中显示视图组

实现重复视图或视图组可以很简单，只需将其[HStack](HStack.zh-Hans.md)或[VStack](VStack.zh-Hans.md)包裹在[ScrollView](ScrollView.zh-Hans.md)内即可。

```swift
ScrollView(.horizontal) {
    HStack {
        ProfileView()
        ProfileView()
        ProfileView()
        ProfileView()
        ProfileView()
    }
}
.frame(maxWidth: 500)
```

如果上面示例代码中的`ProfileView` 的固有内容大小为 200 x 200 点，则[frame(minWidth:idealWidth:maxWidth:minHeight:idealHeight:maxHeight:alignment:)](View/frame_minWidth_idealWidth_maxWidth_minHeight_idealHeight_maxHeight_alignment.zh-Hans.md) 视图修改器应用于[ScrollView](ScrollView.zh-Hans.md) 的最大宽度为 500 点，这将导致堆栈在其内部滚动。



有关使用堆栈将视图分组的介绍，请参阅 [Building-Layouts-with-Stack-Views](Building-Layouts-with-Stack-Views.zh-Hans.md)。

###为你的数据重复视图

使用 [ForEach](ForEach.zh-Hans.md) 为你应用程序中的数据重复视图。从`profiles` 数组中的配置文件数据列表，使用[ForEach](ForEach.zh-Hans.md) 在[HStack](HStack.zh-Hans.md) 中为数组中的每个元素创建一个`ProfileView`。

```swift
ScrollView(.horizontal) {
    HStack {
        ForEach(profiles) { profile in
            ProfileView(profile: profile)
        }
    }
}
.frame(maxWidth: 500)
```



### 考虑对大量视图使用懒堆栈

三个标准堆栈视图[HStack](HStack.zh-Hans.md)、[VStack](VStack.zh-Hans.md) 和 [ZStack](ZStack.zh-Hans.md)在显示时都会加载其包含的视图层次结构，而一次性加载大量视图会导致运行时性能缓慢。

在上例中，`ProfileView` 是一个复合视图，由嵌套的堆栈视图、文本标签和图像视图组成。一次性加载大量配置文件会导致运行速度明显降低。

随着堆栈内视图数量的增加，可以考虑使用 [LazyHStack](LazyHStack.zh-Hans.md) 和 [LazyVStack](LazyVStack.zh-Hans.md) 代替 [HStack](HStack.zh-Hans.md) 和 [VStack](VStack.zh-Hans.md)。懒人堆栈按需加载和渲染子视图，在加载大量子视图时能显著提高性能。



堆栈视图和懒人堆栈具有相似的功能，感觉上可以互换，但在不同的情况下各有优势。堆栈视图一次性加载所有子视图，布局快速可靠，因为系统在加载子视图时知道每个子视图的大小和形状。懒惰堆栈以一定程度的布局正确性换取性能，因为系统只会在子视图可见时才计算它们的几何形状。

在选择要使用的堆栈视图类型时，应始终从标准堆栈视图开始，只有在对代码进行剖析后发现性能有明显改善时，才切换到懒惰堆栈。

### 配置文件查找性能问题

在考虑使用哪种堆栈类型时，请使用 Instruments 工具对应用程序进行剖析，以确定用户界面代码中大量视图在堆栈内加载的区域。

要对 SwiftUI 视图加载进行剖析，请从 Xcode 产品菜单中选择剖析并选择 SwiftUI 剖析模板，从而打开 Instruments 工具。此模板会加载四个工具：View Body、View Properties、Core Animation Commits 和 Time Profiler。这些工具的组合提供了一个很好的起点，让您找到加快应用程序速度的机会。





在对上述代码进行剖析时，View Body 工具显示，1000 个`ProfileView` 实例与[HStack](HStack.zh-Hans.md) 实例同时加载到内存中。在系统加载每个配置文件时，您还可以看到相同数量的 [Image](Image.zh-Hans.md) 视图加载。

在这种情况下，解决办法是用[LazyHStack](LazyHStack.zh-Hans.md) 替换[HStack](HStack.zh-Hans.md)，如下代码所示：

```swift
ScrollView(.horizontal) {
    LazyHStack {
        ForEach(profiles) { profile in
            ProfileView(profile: profile)
        }
    }
}
.frame(maxWidth: 500)
```

运行另一个跟踪结果显示，初始加载视图的数量大幅减少，只有四个`ProfileView` 实例开始可见。您还可以看到总持续时间列也相应减少。



有关使用仪器工具的更多信息，请参阅 [doc://com.apple.documentation/documentation/Xcode/improving-your-app-s-performance]。

## 动态排列一维视图

- 使用懒堆栈视图对数据进行分组**：在懒堆栈视图中将内容分割成逻辑部分。
- **LazyHStack**：一种视图，它将其子视图排列成一条水平增长的线，只在需要时创建项目。
- **LazyVStack**：视图将其子视图排成纵向增长的行，只在需要时创建项目。
- **PinnedScrollableViews**：可固定在滚动视图边界上的视图类型集。


---
source: https://developer.apple.com/documentation/SwiftUI/Creating-Performant-Scrollable-Stacks
crawled: 2025-12-02T17:38:07Z
---

# Creating performant scrollable stacks

**Article**

Display large numbers of repeated views efficiently with scroll views, stack views, and lazy stacks.

## Overview

Your apps often need to display more data within a container view than there is space for on a device’s screen. Horizontal and vertical stacks are a good solution for repeating views or groups of views, but they don’t have a built-in mechanism for scrolling. You can add scrolling by wrapping stacks inside a [ScrollView](ScrollView.zh-Hans.md), and switch to lazy stacks as performance issues arise.

### Display groups of views in a scrollable container

Implementing repeating views or groups of views can be as simple as wrapping them in an [HStack](HStack.zh-Hans.md) or [VStack](VStack.zh-Hans.md) inside a [ScrollView](ScrollView.zh-Hans.md).

```swift
ScrollView(.horizontal) {
    HStack {
        ProfileView()
        ProfileView()
        ProfileView()
        ProfileView()
        ProfileView()
    }
}
.frame(maxWidth: 500)
```

If the `ProfileView` in the example code above has an intrinsic content size of 200 x 200 points, the maximum width of 500 points that the [frame(minWidth:idealWidth:maxWidth:minHeight:idealHeight:maxHeight:alignment:)](View/frame_minWidth_idealWidth_maxWidth_minHeight_idealHeight_maxHeight_alignment.zh-Hans.md) view modifier applies to the [ScrollView](ScrollView.zh-Hans.md) causes the stack to scroll inside it.



For an introduction to using stacks to group views together, see [Building-Layouts-with-Stack-Views](Building-Layouts-with-Stack-Views.zh-Hans.md).

### Repeat views for your data

Use [ForEach](ForEach.zh-Hans.md) to repeat views for the data in your app. From a list of profile data in a `profiles` array, use [ForEach](ForEach.zh-Hans.md) to create one `ProfileView` per element in the array inside an [HStack](HStack.zh-Hans.md).

```swift
ScrollView(.horizontal) {
    HStack {
        ForEach(profiles) { profile in
            ProfileView(profile: profile)
        }
    }
}
.frame(maxWidth: 500)
```



### Consider lazy stacks for large numbers of views

The three standard stack views, [HStack](HStack.zh-Hans.md), [VStack](VStack.zh-Hans.md), and [ZStack](ZStack.zh-Hans.md), all load their contained view hierarchy when they display, and loading large numbers of views all at once can result in slow runtime performance.

In the above example, `ProfileView` is a compound view that consists of nested stack views, text labels, and an image view. Loading a large number of profiles all at once causes a noticeable slowdown.

As the number of views inside a stack grows, consider using a [LazyHStack](LazyHStack.zh-Hans.md) and [LazyVStack](LazyVStack.zh-Hans.md) instead of [HStack](HStack.zh-Hans.md) and [VStack](VStack.zh-Hans.md). Lazy stacks load and render their subviews on-demand, providing significant performance gains when loading large numbers of subviews.



Stack views and lazy stacks have similar functionality, and they may feel interchangeable, but they each have strengths in different situations. Stack views load their child views all at once, making layout fast and reliable, because the system knows the size and shape of every subview as it loads them. Lazy stacks trade some degree of layout correctness for performance, because the system only calculates the geometry for subviews as they become visible.

When choosing the type of stack view to use, always start with a standard stack view and only switch to a lazy stack if profiling your code shows a worthwhile performance improvement.

### Profile to find performance problems

When considering which type of stack to use, use the Instruments tool to profile your application to identify the areas of your user interface code where large numbers of views are loading inside a stack.

To profile SwiftUI view loading, open the Instruments tool by selecting Profile from the Xcode Product menu and choosing the SwiftUI profiling template. This template loads four instruments: View Body, View Properties, Core Animation Commits, and Time Profiler. The combination of these instruments provides a good starting point to find opportunities to speed up your app.





When profiling the above code, the View Body instrument shows that 1,000 `ProfileView` instances load into memory at the same time as the [HStack](HStack.zh-Hans.md). You can also see the same number of [Image](Image.zh-Hans.md) views load as the system loads each profile.

In this case, the solution is to replace the [HStack](HStack.zh-Hans.md) with a [LazyHStack](LazyHStack.zh-Hans.md) as the following code shows:

```swift
ScrollView(.horizontal) {
    LazyHStack {
        ForEach(profiles) { profile in
            ProfileView(profile: profile)
        }
    }
}
.frame(maxWidth: 500)
```

Running another trace shows a drastic reduction in the number of initially loaded views as only four `ProfileView` instances start as visible. You can also see a corresponding decrease in the Total Duration column.



For more information about using the Instruments tool, see [doc://com.apple.documentation/documentation/Xcode/improving-your-app-s-performance].

## Dynamically arranging views in one dimension

- **Grouping data with lazy stack views**: Split content into logical sections inside lazy stack views.
- **LazyHStack**: A view that arranges its children in a line that grows horizontally, creating items only as needed.
- **LazyVStack**: A view that arranges its children in a line that grows vertically, creating items only as needed.
- **PinnedScrollableViews**: A set of view types that may be pinned to the bounds of a scroll view.

