---
来源： https://developer.apple.com/documentation/SwiftUI/Migrating-to-New-Navigation-Types
抓取时间： 2025-12-02T16:15:47Z
---

# 迁移到新的导航类型

**Article**

用导航堆栈和导航分割视图取代导航视图，改进应用程序中的导航行为。

### 概览

如果您的应用程序的最低部署目标是 iOS 16、iPadOS 16、macOS 13、tvOS 16、watchOS 9 或 visionOS 1 或更高版本，请停止使用 [NavigationView](NavigationView.zh-Hans.md)。取而代之的是使用 [NavigationStack](NavigationStack.zh-Hans.md) 和 [NavigationSplitView](NavigationSplitView.zh-Hans.md) 实例。如何使用这些实例取决于您是在一列中执行导航，还是在多列中执行导航。有了这些更新的容器，你就可以更好地控制视图显示、容器配置和编程导航。

### 更新单列导航

如果你的应用程序使用[NavigationView](NavigationView.zh-Hans.md)导航视图样式（人们通过将新视图推送到堆栈来进行导航），请切换到[NavigationStack](NavigationStack.zh-Hans.md)导航视图样式。

尤其是，不要再这样做了：

```swift
NavigationView { // This is deprecated.
    /* content */
}
.navigationViewStyle(.stack)
```

取而代之的是创建一个导航堆栈：

```swift
NavigationStack {
    /* content */
}
```

### 更新多栏导航

如果您的应用程序使用双栏或三栏[NavigationView](NavigationView.zh-Hans.md)，或在某些情况下使用多栏而在其他情况下使用单栏的应用程序（这是在 iPhone 和 iPad 上运行的典型应用程序），请切换到[NavigationSplitView](NavigationSplitView.zh-Hans.md)。

而不是使用双栏导航视图：

```swift
NavigationView { // This is deprecated.
    /* column 1 */
    /* column 2 */
}
```

使用[init(sidebar:detail:)](NavigationSplitView/init_sidebar_detail.zh-Hans.md) 初始化程序创建具有明确侧边栏和详细内容的导航分栏视图：

```swift
NavigationSplitView {
    /* column 1 */
} detail: {
    /* column 2 */
}
```

同样，也可以不使用三栏导航视图：

```swift
NavigationView { // This is deprecated.
    /* column 1 */
    /* column 2 */
    /* column 3 */
}
```

使用[init(sidebar:content:detail:)](NavigationSplitView/init_sidebar_content_detail.zh-Hans.md) 初始化程序创建一个包含明确侧边栏、内容和详细信息组件的导航分割视图：

```swift
NavigationSplitView {
    /* column 1 */
} content: {
    /* column 2 */
} detail: {
    /* column 3 */
}
```

如果需要在一列中进行导航，可在该列中嵌入导航堆栈。这种安排可以更精细地控制每一列显示的内容。[NavigationSplitView](NavigationSplitView.zh-Hans.md)还能让你自定义列的可见性和宽度。

### 更新程序化导航

如果使用具有`isActive` 输入参数的[NavigationLink](NavigationLink.zh-Hans.md) 初始化程序之一执行编程导航，请将自动化移至外层堆栈。具体做法是将导航链接改为使用[init(value:label:)](NavigationLink/init_value_label.zh-Hans.md) 初始化程序，然后使用其中一个需要路径输入的导航栈初始化程序，如 [init(path:root:)](NavigationStack/init_path_root.zh-Hans.md)。

例如，如果你有一个导航视图，其中的链接会根据单个状态变量激活：

```swift
@State private var isShowingPurple = false
@State private var isShowingPink = false
@State private var isShowingOrange = false

var body: some View {
    NavigationView { // This is deprecated.
        List {
            NavigationLink("Purple", isActive: $isShowingPurple) {
                ColorDetail(color: .purple)
            }
            NavigationLink("Pink", isActive: $isShowingPink) {
                ColorDetail(color: .pink)
            }
            NavigationLink("Orange", isActive: $isShowingOrange) {
                ColorDetail(color: .orange)
            }
        }
    }
    .navigationViewStyle(.stack) 
}
```

当代码的其他部分将其中一个状态变量设置为 true 时，具有匹配标记的导航链接就会响应激活。

将此重写为接收路径输入的导航栈：

```swift
@State private var path: [Color] = [] // Nothing on the stack by default.

var body: some View {
    NavigationStack(path: $path) {
        List {
            NavigationLink("Purple", value: .purple)
            NavigationLink("Pink", value: .pink)
            NavigationLink("Orange", value: .orange)
        }
        .navigationDestination(for: Color.self) { color in
            ColorDetail(color: color)
        }
    }
}
```

该版本使用[navigationDestination(for:destination:)](View/navigationDestination_for_destination.zh-Hans.md) 视图修饰符将显示的数据从相应的视图中分离出来。这样，`path` 数组就可以代表堆栈中的每个视图。对数组所做的更改会影响容器现在显示的内容，以及人们在堆栈中浏览时遇到的内容。如果使用[NavigationPath](NavigationPath.zh-Hans.md) 来存储路径信息，而不是一个普通的数据集合，就可以支持更复杂的编程导航。更多信息，请参阅 [NavigationStack](NavigationStack.zh-Hans.md)。

### 更新基于选择的导航

如果你对[List](List.zh-Hans.md) 元素执行编程导航，而这些元素使用了带有`selection` 输入参数的[NavigationLink](NavigationLink.zh-Hans.md) 初始化器，你就可以将选择移动到列表中。例如，假设有一个导航视图，其中的链接会根据`selection` 状态变量激活：

```swift
let colors: [Color] = [.purple, .pink, .orange]
@State private var selection: Color? = nil // Nothing selected by default.

var body: some View {
    NavigationView { // This is deprecated.
        List {
            ForEach(colors, id: \.self) { color in
                NavigationLink(color.description, tag: color, selection: $selection) {
                    ColorDetail(color: color)
                }
            }
        }
        Text("Pick a color")
    }
}
```

使用相同的属性，可以将正文重写为

```swift
var body: some View {
    NavigationSplitView {
        List(colors, id: \.self, selection: $selection) { color in
            NavigationLink(color.description, value: color)
        }
    } detail: {
        if let color = selection {
            ColorDetail(color: color)
        } else {
            Text("Pick a color")
        }
    }
}
```

列表与导航逻辑相协调，因此在代码的另一部分改变选择状态变量，就会激活相应颜色的导航链接。同样，如果有人选择了与特定颜色相关联的导航链接，列表就会更新选择值，以便代码的其他部分可以读取。

###提供向后兼容的可用性检查

如果您的应用程序需要在早于 iOS 16、iPadOS 16、macOS 13、tvOS 16、watchOS 9 或 visionOS 1 的平台版本上运行，您可以使用 [https://docs.swift.org/swift-book/documentation/the-swift-programming-language/statements/#Availability-Condition] 开始迁移，同时继续支持旧版客户端。例如，你可以创建一个自定义封装视图，有条件地使用[NavigationSplitView](NavigationSplitView.zh-Hans.md)或[NavigationView](NavigationView.zh-Hans.md)：

```swift
struct NavigationSplitViewWrapper<Sidebar, Content, Detail>: View
    where Sidebar: View, Content: View, Detail: View
{
    private var sidebar: Sidebar
    private var content: Content
    private var detail: Detail
    
    init(
        @ViewBuilder sidebar: () -> Sidebar,
        @ViewBuilder content: () -> Content,
        @ViewBuilder detail:  () -> Detail
    ) {
        self.sidebar = sidebar()
        self.content = content()
        self.detail = detail()
    }
    
    var body: some View {
        if #available(iOS 16, macOS 13, tvOS 16, watchOS 9, visionOS 1, *) {
            // Use the latest API.
            NavigationSplitView {
                sidebar
            } content: {
                content
            } detail: {
                detail
            }
        } else {
            // Support previous platform versions.
            NavigationView {
                sidebar
                content
                detail
            }
            .navigationViewStyle(.columns)
        }
    }
}
```

自定义包装器以满足应用程序的需求。例如，您可以在可用性检查的相应分支中的[navigationSplitViewStyle(_:)](View/navigationSplitViewStyle.zh-Hans.md)中添加类似[NavigationSplitView](NavigationSplitView.zh-Hans.md)的导航分割视图样式修饰符。

## 以列的形式显示视图

- 为你的 SwiftUI 应用程序带来强大的导航结构**：使用导航链接、堆栈、目的地和路径为所有平台提供简化的体验，以及深度链接和状态恢复等行为。
- **NavigationSplitView**：以两列或三列显示视图的视图，在前导列中的选择可控制后续列的显示。
- **navigationSplitViewStyle(_:)**：设置该视图中导航分割视图的样式。
- **navigationSplitViewColumnWidth(_:)**：为包含此视图的列设置固定的首选宽度。
- **navigationSplitViewColumnWidth(min:ideal:max:)**：为包含此视图的列设置灵活的首选宽度。
- **NavigationSplitViewVisibility**：导航分割视图中前导列的可见性。
- **NavigationLink**：控制导航演示的视图。


---
source: https://developer.apple.com/documentation/SwiftUI/Migrating-to-New-Navigation-Types
crawled: 2025-12-02T16:15:47Z
---

# Migrating to new navigation types

**Article**

Improve navigation behavior in your app by replacing navigation views with navigation stacks and navigation split views.

## Overview

If your app has a minimum deployment target of iOS 16, iPadOS 16, macOS 13, tvOS 16, watchOS 9, or visionOS 1, or later, transition away from using [NavigationView](NavigationView.zh-Hans.md). In its place, use [NavigationStack](NavigationStack.zh-Hans.md) and [NavigationSplitView](NavigationSplitView.zh-Hans.md) instances. How you use these depends on whether you perform navigation in one column or across multiple columns. With these newer containers, you get better control over view presentation, container configuration, and programmatic navigation.

### Update single column navigation

If your app uses a [NavigationView](NavigationView.zh-Hans.md) that you style using the [stack](NavigationViewStyle/stack.zh-Hans.md) navigation view style, where people navigate by pushing a new view onto a stack, switch to [NavigationStack](NavigationStack.zh-Hans.md).

In particular, stop doing this:

```swift
NavigationView { // This is deprecated.
    /* content */
}
.navigationViewStyle(.stack)
```

Instead, create a navigation stack:

```swift
NavigationStack {
    /* content */
}
```

### Update multicolumn navigation

If your app uses a two- or three-column [NavigationView](NavigationView.zh-Hans.md), or for apps that have multiple columns in some cases and a single column in others — which is typical for apps that run on iPhone and iPad — switch to [NavigationSplitView](NavigationSplitView.zh-Hans.md).

Instead of using a two-column navigation view:

```swift
NavigationView { // This is deprecated.
    /* column 1 */
    /* column 2 */
}
```

Create a navigation split view that has explicit sidebar and detail content using the [init(sidebar:detail:)](NavigationSplitView/init_sidebar_detail.zh-Hans.md) initializer:

```swift
NavigationSplitView {
    /* column 1 */
} detail: {
    /* column 2 */
}
```

Similarly, instead of using a three-column navigation view:

```swift
NavigationView { // This is deprecated.
    /* column 1 */
    /* column 2 */
    /* column 3 */
}
```

Create a navigation split view that has explicit sidebar, content, and detail components using the [init(sidebar:content:detail:)](NavigationSplitView/init_sidebar_content_detail.zh-Hans.md) initializer:

```swift
NavigationSplitView {
    /* column 1 */
} content: {
    /* column 2 */
} detail: {
    /* column 3 */
}
```

If you need navigation within a column, embed a navigation stack in that column. This arrangement provides finer control over what each column displays. [NavigationSplitView](NavigationSplitView.zh-Hans.md) also enables you to customize column visibility and width.

### Update programmatic navigation

If you perform programmatic navigation using one of the [NavigationLink](NavigationLink.zh-Hans.md) initializers that has an `isActive` input parameter, move the automation to the enclosing stack. Do this by changing your navigation links to use the [init(value:label:)](NavigationLink/init_value_label.zh-Hans.md) initializer, then use one of the navigation stack initializers that takes a path input, like [init(path:root:)](NavigationStack/init_path_root.zh-Hans.md).

For example, if you have a navigation view with links that activate in response to individual state variables:

```swift
@State private var isShowingPurple = false
@State private var isShowingPink = false
@State private var isShowingOrange = false

var body: some View {
    NavigationView { // This is deprecated.
        List {
            NavigationLink("Purple", isActive: $isShowingPurple) {
                ColorDetail(color: .purple)
            }
            NavigationLink("Pink", isActive: $isShowingPink) {
                ColorDetail(color: .pink)
            }
            NavigationLink("Orange", isActive: $isShowingOrange) {
                ColorDetail(color: .orange)
            }
        }
    }
    .navigationViewStyle(.stack) 
}
```

When some other part of your code sets one of the state variables to true, the navigation link that has the matching tag activates in response.

Rewrite this as a navigation stack that takes a path input:

```swift
@State private var path: [Color] = [] // Nothing on the stack by default.

var body: some View {
    NavigationStack(path: $path) {
        List {
            NavigationLink("Purple", value: .purple)
            NavigationLink("Pink", value: .pink)
            NavigationLink("Orange", value: .orange)
        }
        .navigationDestination(for: Color.self) { color in
            ColorDetail(color: color)
        }
    }
}
```

This version uses the [navigationDestination(for:destination:)](View/navigationDestination_for_destination.zh-Hans.md) view modifier to detach the presented data from the corresponding view. That makes it possible for the `path` array to represent every view on the stack. Changes that you make to the array affect what the container displays right now, as well as what people encounter as they navigate through the stack. You can support even more sophisticated programmatic navigation if you use a [NavigationPath](NavigationPath.zh-Hans.md) to store the path information, rather than a plain collection of data. For more information, see [NavigationStack](NavigationStack.zh-Hans.md).

### Update selection-based navigation

If you perform programmatic navigation on [List](List.zh-Hans.md) elements that use one of the [NavigationLink](NavigationLink.zh-Hans.md) initializers with a `selection` input parameter, you can move the selection to the list. For example, suppose you have a navigation view with links that activate in response to a `selection` state variable:

```swift
let colors: [Color] = [.purple, .pink, .orange]
@State private var selection: Color? = nil // Nothing selected by default.

var body: some View {
    NavigationView { // This is deprecated.
        List {
            ForEach(colors, id: \.self) { color in
                NavigationLink(color.description, tag: color, selection: $selection) {
                    ColorDetail(color: color)
                }
            }
        }
        Text("Pick a color")
    }
}
```

Using the same properties, you can rewrite the body as:

```swift
var body: some View {
    NavigationSplitView {
        List(colors, id: \.self, selection: $selection) { color in
            NavigationLink(color.description, value: color)
        }
    } detail: {
        if let color = selection {
            ColorDetail(color: color)
        } else {
            Text("Pick a color")
        }
    }
}
```

The list coordinates with the navigation logic so that changing the selection state variable in another part of your code activates the navigation link with the corresponding color. Similarly, if someone chooses the navigation link associated with a particular color, the list updates the selection value that other parts of your code can read.

### Provide backward compatibility with an availability check

If your app needs to run on platform versions earlier than iOS 16, iPadOS 16, macOS 13, tvOS 16, watchOS 9, or visionOS 1, you can start migration while continuing to support older clients by using an [https://docs.swift.org/swift-book/documentation/the-swift-programming-language/statements/#Availability-Condition]. For example, you can create a custom wrapper view that conditionally uses either [NavigationSplitView](NavigationSplitView.zh-Hans.md) or [NavigationView](NavigationView.zh-Hans.md):

```swift
struct NavigationSplitViewWrapper<Sidebar, Content, Detail>: View
    where Sidebar: View, Content: View, Detail: View
{
    private var sidebar: Sidebar
    private var content: Content
    private var detail: Detail
    
    init(
        @ViewBuilder sidebar: () -> Sidebar,
        @ViewBuilder content: () -> Content,
        @ViewBuilder detail:  () -> Detail
    ) {
        self.sidebar = sidebar()
        self.content = content()
        self.detail = detail()
    }
    
    var body: some View {
        if #available(iOS 16, macOS 13, tvOS 16, watchOS 9, visionOS 1, *) {
            // Use the latest API.
            NavigationSplitView {
                sidebar
            } content: {
                content
            } detail: {
                detail
            }
        } else {
            // Support previous platform versions.
            NavigationView {
                sidebar
                content
                detail
            }
            .navigationViewStyle(.columns)
        }
    }
}
```

Customize the wrapper to meet your app’s needs. For example, you can add a navigation split view style modifier like [navigationSplitViewStyle(_:)](View/navigationSplitViewStyle.zh-Hans.md) to the [NavigationSplitView](NavigationSplitView.zh-Hans.md) in the appropriate branch of the availability check.

## Presenting views in columns

- **Bringing robust navigation structure to your SwiftUI app**: Use navigation links, stacks, destinations, and paths to provide a streamlined experience for all platforms, as well as behaviors such as deep linking and state restoration.
- **NavigationSplitView**: A view that presents views in two or three columns, where selections in leading columns control presentations in subsequent columns.
- **navigationSplitViewStyle(_:)**: Sets the style for navigation split views within this view.
- **navigationSplitViewColumnWidth(_:)**: Sets a fixed, preferred width for the column containing this view.
- **navigationSplitViewColumnWidth(min:ideal:max:)**: Sets a flexible, preferred width for the column containing this view.
- **NavigationSplitViewVisibility**: The visibility of the leading columns in a navigation split view.
- **NavigationLink**: A view that controls a navigation presentation.

