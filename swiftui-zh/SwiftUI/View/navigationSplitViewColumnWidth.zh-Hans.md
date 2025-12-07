--- 来源：https://developer.apple.com/documentation/SwiftUI/View/navigationSplitViewColumnWidth(_:)

抓取时间：2025-12-02T16:15:49Z

---

# navigationSplitViewColumnWidth(_:)

**实例方法**

为包含此视图的列设置一个固定的首选宽度。

## 声明

```swift
nonisolated func navigationSplitViewColumnWidth(_ width: CGFloat) -> some View

```

## 说明

将此修饰符应用于 [NavigationSplitView](../NavigationSplitView.zh-Hans.md) 中列的内容，以指定该列的固定首选宽度。如果需要指定灵活的宽度，请使用 [navigationSplitViewColumnWidth(min:ideal:max:)](navigationSplitViewColumnWidth_min_ideal_max.zh-Hans.md)。

以下示例展示了一个三列导航拆分视图，其中第一列的首选宽度为 150 点，第二列的首选宽度可在 150 到 400 点之间灵活调整：

```swift
NavigationSplitView {
    MySidebar()
        .navigationSplitViewColumnWidth(150)
} contents: {
    MyContents()
        .navigationSplitViewColumnWidth(
            min: 150, ideal: 200, max: 400)
} detail: {
    MyDetail()
}
```

只有部分平台支持调整列宽。如果您指定的宽度在当前显示环境中不受支持，SwiftUI 可能会使用不同的列宽。

## 以列的形式呈现视图

- **为您的 SwiftUI 应用带来强大的导航结构**：使用导航链接、堆栈、目标和路径，为所有平台提供流畅的体验，以及深度链接和状态恢复等功能。

- **迁移到新的导航类型**：通过将导航视图替换为导航堆栈和导航拆分视图，改进应用中的导航行为。

- **NavigationSplitView**：一种以两列或三列形式呈现视图的视图，其中前几列中的选择会控制后续列的呈现方式。

- **navigationSplitViewStyle(_:)**：设置此视图内导航拆分视图的样式。

- **navigationSplitViewColumnWidth(min:ideal:max:)**：设置包含此视图的列的灵活首选宽度。

- **NavigationSplitViewVisibility**：导航拆分视图中前导列的可见性。

- **NavigationLink**：控制导航呈现方式的视图。


---
source: https://developer.apple.com/documentation/SwiftUI/View/navigationSplitViewColumnWidth(_:)
crawled: 2025-12-02T16:15:49Z
---

# navigationSplitViewColumnWidth(_:)

**Instance Method**

Sets a fixed, preferred width for the column containing this view.

## Declaration

```swift
nonisolated func navigationSplitViewColumnWidth(_ width: CGFloat) -> some View

```

## Discussion

Apply this modifier to the content of a column in a [NavigationSplitView](../NavigationSplitView.zh-Hans.md) to specify a fixed preferred width for the column. Use [navigationSplitViewColumnWidth(min:ideal:max:)](navigationSplitViewColumnWidth_min_ideal_max.zh-Hans.md) if you need to specify a flexible width.

The following example shows a three-column navigation split view where the first column has a preferred width of 150 points, and the second column has a flexible, preferred width between 150 and 400 points:

```swift
NavigationSplitView {
    MySidebar()
        .navigationSplitViewColumnWidth(150)
} contents: {
    MyContents()
        .navigationSplitViewColumnWidth(
            min: 150, ideal: 200, max: 400)
} detail: {
    MyDetail()
}
```

Only some platforms enable resizing columns. If you specify a width that the current presentation environment doesn’t support, SwiftUI may use a different width for your column.

## Presenting views in columns

- **Bringing robust navigation structure to your SwiftUI app**: Use navigation links, stacks, destinations, and paths to provide a streamlined experience for all platforms, as well as behaviors such as deep linking and state restoration.
- **Migrating to new navigation types**: Improve navigation behavior in your app by replacing navigation views with navigation stacks and navigation split views.
- **NavigationSplitView**: A view that presents views in two or three columns, where selections in leading columns control presentations in subsequent columns.
- **navigationSplitViewStyle(_:)**: Sets the style for navigation split views within this view.
- **navigationSplitViewColumnWidth(min:ideal:max:)**: Sets a flexible, preferred width for the column containing this view.
- **NavigationSplitViewVisibility**: The visibility of the leading columns in a navigation split view.
- **NavigationLink**: A view that controls a navigation presentation.

