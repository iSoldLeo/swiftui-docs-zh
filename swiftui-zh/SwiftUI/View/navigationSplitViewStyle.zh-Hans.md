--- 来源：https://developer.apple.com/documentation/SwiftUI/View/navigationSplitViewStyle(_:)

抓取时间：2025-11-30T20:01:02Z

---

# navigationSplitViewStyle(_:)

**实例方法**

设置此视图中导航拆分视图的样式。

## 声明

```swift
nonisolated func navigationSplitViewStyle<S>(_ style: S) -> some View where S : NavigationSplitViewStyle

```

## 参数

- **style**：要设置的样式。

## 返回值

使用指定导航拆分视图样式的视图。

## 以列形式呈现视图

- **为您的 SwiftUI 应用带来强大的导航结构**：使用导航链接、堆栈、目标和路径，为所有平台提供流畅的体验，以及深度链接和状态恢复等功能。

- **迁移到新的导航类型**：通过将导航视图替换为导航堆栈和导航拆分视图，改进应用中的导航行为。

- **NavigationSplitView**：一种以两列或三列形式呈现视图的视图，其中前几列中的选择控制后续列的显示。

- **navigationSplitViewColumnWidth(_:)**：为包含此视图的列设置固定的首选宽度。

- **navigationSplitViewColumnWidth(min:ideal:max:)**：为包含此视图的列设置灵活的首选宽度。

- **NavigationSplitViewVisibility**：导航拆分视图中前几列的可见性。

- **NavigationLink**：一种控制导航显示的视图。


---
source: https://developer.apple.com/documentation/SwiftUI/View/navigationSplitViewStyle(_:)
crawled: 2025-11-30T20:01:02Z
---

# navigationSplitViewStyle(_:)

**Instance Method**

Sets the style for navigation split views within this view.

## Declaration

```swift
nonisolated func navigationSplitViewStyle<S>(_ style: S) -> some View where S : NavigationSplitViewStyle

```

## Parameters

- **style**: The style to set.

## Return Value

A view that uses the specified navigation split view style.

## Presenting views in columns

- **Bringing robust navigation structure to your SwiftUI app**: Use navigation links, stacks, destinations, and paths to provide a streamlined experience for all platforms, as well as behaviors such as deep linking and state restoration.
- **Migrating to new navigation types**: Improve navigation behavior in your app by replacing navigation views with navigation stacks and navigation split views.
- **NavigationSplitView**: A view that presents views in two or three columns, where selections in leading columns control presentations in subsequent columns.
- **navigationSplitViewColumnWidth(_:)**: Sets a fixed, preferred width for the column containing this view.
- **navigationSplitViewColumnWidth(min:ideal:max:)**: Sets a flexible, preferred width for the column containing this view.
- **NavigationSplitViewVisibility**: The visibility of the leading columns in a navigation split view.
- **NavigationLink**: A view that controls a navigation presentation.

