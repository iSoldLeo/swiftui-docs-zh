--- 来源：https://developer.apple.com/documentation/SwiftUI/NavigationLink

抓取时间：2025-12-02T16:15:52Z

---

# NavigationLink

**Structure**

用于控制导航呈现的视图。

## 声明

```swift
struct NavigationLink<Label, Destination> where Label : View, Destination : View
```

## 概述

用户点击或轻触导航链接，即可在 [NavigationStack](NavigationStack.zh-Hans.md) 或 [NavigationSplitView](NavigationSplitView.zh-Hans.md) 内显示视图。您可以通过在链接的 `label` 闭包中提供视图内容来控制链接的视觉外观。例如，您可以使用 [Label](Label.zh-Hans.md) 来显示链接：

```swift
NavigationLink {
    FolderDetail(id: workFolder.id)
} label: {
    Label("Work Folder", systemImage: "folder")
}
```

对于仅包含文本的链接，您可以使用便捷的初始化器，该初始化器接受一个字符串并为您创建一个 [Text](Text.zh-Hans.md) 视图：

```swift
NavigationLink("Work Folder") {
    FolderDetail(id: workFolder.id)
}
```

### 链接到目标视图

您可以通过在 `destination` 闭包中提供目标视图来初始化链接，从而实现导航。例如，考虑一个 `ColorDetail` 视图，它会填充颜色：

```swift
struct ColorDetail: View {
    var color: Color

    var body: some View {
        color.navigationTitle(color.description)
    }
}
```

以下 [NavigationStack](NavigationStack.zh-Hans.md) 提供了三个指向颜色详情视图的链接：

```swift
NavigationStack {
    List {
        NavigationLink("Mint") { ColorDetail(color: .mint) }
        NavigationLink("Pink") { ColorDetail(color: .pink) }
        NavigationLink("Teal") { ColorDetail(color: .teal) }
    }
    .navigationTitle("Colors")
}
```

### 创建展示链接

或者，您可以使用导航链接，根据显示的数据值执行导航。为此，请在导航堆栈中使用 [navigationDestination(for:destination:)](View/navigationDestination_for_destination.zh-Hans.md) 视图修饰符，将视图与某种数据类型关联起来，然后通过导航链接显示该数据类型的值。以下示例将前面的示例重新实现为一系列展示链接：

```swift
NavigationStack {
    List {
        NavigationLink("Mint", value: Color.mint)
        NavigationLink("Pink", value: Color.pink)
        NavigationLink("Teal", value: Color.teal)
    }
    .navigationDestination(for: Color.self) { color in
        ColorDetail(color: color)
    }
    .navigationTitle("Colors")
}
```

将视图与数据分离有助于实现程序化导航，因为您可以通过记录显示的数据来管理导航状态。

### 以编程方式控制演示链接

要以编程方式进行导航，请引入一个状态变量来跟踪堆栈中的项目。例如，您可以创建一个颜色数组来存储上一个示例中的堆栈状态，并将其初始化为空数组，以便从空堆栈开始：

```swift
@State private var colors: [Color] = []
```

然后将 [Binding](Binding.zh-Hans.md) 传递给导航堆栈的状态：

```swift
NavigationStack(path: $colors) {
    // ...
}
```

您可以使用该数组来观察堆栈的当前状态。您还可以修改该数组来更改堆栈的内容。例如，您可以使用以下方法以编程方式将 [blue](ShapeStyle/blue.zh-Hans.md) 添加到数组中，并导航到新的颜色详情视图：

```swift
func showBlue() {
    colors.append(.blue)
}
```

### 与列表协调

您还可以使用导航链接来控制 [List](List.zh-Hans.md) 在 [NavigationSplitView](NavigationSplitView.zh-Hans.md) 中的选择：

```swift
let colors: [Color] = [.mint, .pink, .teal]
@State private var selection: Color? // Nothing selected by default.

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

列表与导航逻辑协调，因此，在代码的其他部分更改选择状态变量会激活具有相应颜色的导航链接。同样，如果用户选择与特定颜色关联的导航链接，列表会更新代码其他部分可以读取的选择值。

## 显示目标视图

- **init(_:destination:)**：创建一个显示目标视图的导航链接，该链接带有一个文本标签，该标签由链接根据本地化字符串键生成。

- **init(destination:label:)**：创建一个导航链接，用于显示目标视图。

## 显示值

- **init(_:value:)**：创建一个导航链接，用于显示与可编码值对应的视图，并带有链接根据本地化字符串键生成的文本标签。

- **init(value:label:)**：创建一个导航链接，用于显示与可编码值对应的视图。

## 配置链接

- **isDetailLink(_:)**：将导航链接的目标视图设置为包含它的导航视图的详细信息组件。

## 已弃用的符号

- **已弃用的符号**：查看已弃用的导航链接初始化器。

## 以列形式呈现视图

- **为您的 SwiftUI 应用带来强大的导航结构**：使用导航链接、堆栈、目标和路径，为所有平台提供流畅的体验，并支持深度链接和状态恢复等功能。

- **迁移到新的导航类型**：通过将导航视图替换为导航堆栈和导航拆分视图，改进应用中的导航行为。

- **NavigationSplitView**：以两列或三列形式呈现视图，其中前几列中的选择控制后续列的呈现方式。

- **navigationSplitViewStyle(_:)**：设置此视图中导航拆分视图的样式。

- **navigationSplitViewColumnWidth(_:)**：设置包含此视图的列的固定首选宽度。

- **navigationSplitViewColumnWidth(min:ideal:max:)**：设置包含此视图的列的灵活首选宽度。

- **NavigationSplitViewVisibility**：导航拆分视图中前导列的可见性。

## 符合

- 视图


---
source: https://developer.apple.com/documentation/SwiftUI/NavigationLink
crawled: 2025-12-02T16:15:52Z
---

# NavigationLink

**Structure**

A view that controls a navigation presentation.

## Declaration

```swift
struct NavigationLink<Label, Destination> where Label : View, Destination : View
```

## Overview

People click or tap a navigation link to present a view inside a [NavigationStack](NavigationStack.zh-Hans.md) or [NavigationSplitView](NavigationSplitView.zh-Hans.md). You control the visual appearance of the link by providing view content in the link’s `label` closure. For example, you can use a [Label](Label.zh-Hans.md) to display a link:

```swift
NavigationLink {
    FolderDetail(id: workFolder.id)
} label: {
    Label("Work Folder", systemImage: "folder")
}
```

For a link composed only of text, you can use one of the convenience initializers that takes a string and creates a [Text](Text.zh-Hans.md) view for you:

```swift
NavigationLink("Work Folder") {
    FolderDetail(id: workFolder.id)
}
```

### Link to a destination view

You can perform navigation by initializing a link with a destination view that you provide in the `destination` closure. For example, consider a `ColorDetail` view that fills itself with a color:

```swift
struct ColorDetail: View {
    var color: Color

    var body: some View {
        color.navigationTitle(color.description)
    }
}
```

The following [NavigationStack](NavigationStack.zh-Hans.md) presents three links to color detail views:

```swift
NavigationStack {
    List {
        NavigationLink("Mint") { ColorDetail(color: .mint) }
        NavigationLink("Pink") { ColorDetail(color: .pink) }
        NavigationLink("Teal") { ColorDetail(color: .teal) }
    }
    .navigationTitle("Colors")
}
```

### Create a presentation link

Alternatively, you can use a navigation link to perform navigation based on a presented data value. To support this, use the [navigationDestination(for:destination:)](View/navigationDestination_for_destination.zh-Hans.md) view modifier inside a navigation stack to associate a view with a kind of data, and then present a value of that data type from a navigation link. The following example reimplements the previous example as a series of presentation links:

```swift
NavigationStack {
    List {
        NavigationLink("Mint", value: Color.mint)
        NavigationLink("Pink", value: Color.pink)
        NavigationLink("Teal", value: Color.teal)
    }
    .navigationDestination(for: Color.self) { color in
        ColorDetail(color: color)
    }
    .navigationTitle("Colors")
}
```

Separating the view from the data facilitates programmatic navigation because you can manage navigation state by recording the presented data.

### Control a presentation link programmatically

To navigate programmatically, introduce a state variable that tracks the items on a stack. For example, you can create an array of colors to store the stack state from the previous example, and initialize it as an empty array to start with an empty stack:

```swift
@State private var colors: [Color] = []
```

Then pass a [Binding](Binding.zh-Hans.md) to the state to the navigation stack:

```swift
NavigationStack(path: $colors) {
    // ...
}
```

You can use the array to observe the current state of the stack. You can also modify the array to change the contents of the stack. For example, you can programmatically add [blue](ShapeStyle/blue.zh-Hans.md) to the array, and navigation to a new color detail view using the following method:

```swift
func showBlue() {
    colors.append(.blue)
}
```

### Coordinate with a list

You can also use a navigation link to control [List](List.zh-Hans.md) selection in a [NavigationSplitView](NavigationSplitView.zh-Hans.md):

```swift
let colors: [Color] = [.mint, .pink, .teal]
@State private var selection: Color? // Nothing selected by default.

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

## Presenting a destination view

- **init(_:destination:)**: Creates a navigation link that presents a destination view, with a text label that the link generates from a localized string key.
- **init(destination:label:)**: Creates a navigation link that presents the destination view.

## Presenting a value

- **init(_:value:)**: Creates a navigation link that presents the view corresponding to a codable value, with a text label that the link generates from a localized string key.
- **init(value:label:)**: Creates a navigation link that presents the view corresponding to a codable value.

## Configuring the link

- **isDetailLink(_:)**: Sets the navigation link to present its destination as the detail component of the containing navigation view.

## Deprecated symbols

- **Deprecated symbols**: Review deprecated navigation link initializers.

## Presenting views in columns

- **Bringing robust navigation structure to your SwiftUI app**: Use navigation links, stacks, destinations, and paths to provide a streamlined experience for all platforms, as well as behaviors such as deep linking and state restoration.
- **Migrating to new navigation types**: Improve navigation behavior in your app by replacing navigation views with navigation stacks and navigation split views.
- **NavigationSplitView**: A view that presents views in two or three columns, where selections in leading columns control presentations in subsequent columns.
- **navigationSplitViewStyle(_:)**: Sets the style for navigation split views within this view.
- **navigationSplitViewColumnWidth(_:)**: Sets a fixed, preferred width for the column containing this view.
- **navigationSplitViewColumnWidth(min:ideal:max:)**: Sets a flexible, preferred width for the column containing this view.
- **NavigationSplitViewVisibility**: The visibility of the leading columns in a navigation split view.

## Conforms To

- View

