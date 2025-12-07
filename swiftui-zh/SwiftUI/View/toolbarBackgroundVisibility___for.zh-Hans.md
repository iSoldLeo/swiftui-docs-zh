--- 来源：https://developer.apple.com/documentation/swiftui/view/toolbarbackgroundvisibility(_:for:)

抓取时间：2025-12-02T16:16:10Z

---

# toolbarBackgroundVisibility(_:for:)

**实例方法**

指定由 SwiftUI 管理的工具栏上背景的首选可见性。

## 声明

```swift
nonisolated func toolbarBackgroundVisibility(_ visibility: Visibility, for bars: ToolbarPlacement...) -> some View

```

## 参数

- **visibility**：工具栏背景的首选可见性。

- **bars**：要更新配色方案的工具栏，如果为空则为 [automatic](../ToolbarPlacement/automatic.zh-Hans.md)。

## 说明

首选可见性会向上传递到渲染工具栏的最近的容器。在 iOS 中，这可能是 [NavigationView](../NavigationView.zh-Hans.md) 或 [TabView](../TabView.zh-Hans.md)，在 macOS 中，这可能是 [WindowGroup](../WindowGroup.zh-Hans.md) 的根视图。

在 iOS 中，[automatic](../ToolbarPlacement/automatic.zh-Hans.md) 的值会使标签栏或导航栏背景的可见性取决于 [List](../List.zh-Hans.md) 或 [ScrollView](../ScrollView.zh-Hans.md) 的位置。例如，当标签栏与滚动视图内容的底部边缘对齐时，其背景会变为透明。

指定 [visible](../Visibility/visible.zh-Hans.md) 的值可确保无论滚动视图或列表滚动到何处，栏的背景始终可见。

此示例展示了一种视图，该视图在选中中间标签时始终显示标签栏：

```swift
TabView {
    FirstTab()
    MiddleTab()
        .toolbarBackgroundVisibility(.visible, for: .tabBar)
    LastTab()
}
```

您可以设置多个位置，以便一次性自定义多个工具栏，如下例所示：

```swift
TabView {
    NavigationView {
        ContentView()
            .toolbarBackgroundVisibility(
                .visible, for: .navigationBar, .tabBar)
    }
}
```

## 设置工具栏可见性

- **toolbar(_:for:)**：指定由 SwiftUI 管理的工具栏的可见性。

- **toolbarVisibility(_:for:)**：指定由 SwiftUI 管理的工具栏的可见性。

- **ToolbarPlacement**：工具栏的位置。

- **ContentToolbarPlacement**


---
source: https://developer.apple.com/documentation/swiftui/view/toolbarbackgroundvisibility(_:for:)
crawled: 2025-12-02T16:16:10Z
---

# toolbarBackgroundVisibility(_:for:)

**Instance Method**

Specifies the preferred visibility of backgrounds on a bar managed by SwiftUI.

## Declaration

```swift
nonisolated func toolbarBackgroundVisibility(_ visibility: Visibility, for bars: ToolbarPlacement...) -> some View

```

## Parameters

- **visibility**: The preferred visibility of the background of the bar.
- **bars**: The bars to update the color scheme of or [automatic](../ToolbarPlacement/automatic.zh-Hans.md) if empty.

## Discussion

The preferred visibility flows up to the nearest container that renders a bar. This could be a [NavigationView](../NavigationView.zh-Hans.md) or [TabView](../TabView.zh-Hans.md) in iOS, or the root view of a [WindowGroup](../WindowGroup.zh-Hans.md) in macOS.

In iOS, a value of [automatic](../ToolbarPlacement/automatic.zh-Hans.md) makes the visibility of a tab bar or navigation bar background depend on where a [List](../List.zh-Hans.md) or [ScrollView](../ScrollView.zh-Hans.md) settles. For example, when aligned to the bottom edge of of a scroll view’s content, the background of a tab bar becomes transparent.

Specify a value of [visible](../Visibility/visible.zh-Hans.md) to ensure that the background of a bar remains visible regardless of where any scroll view or list stops scrolling.

This example shows a view that prefers to always have the tab bar visible when the middle tab is selected:

```swift
TabView {
    FirstTab()
    MiddleTab()
        .toolbarBackgroundVisibility(.visible, for: .tabBar)
    LastTab()
}
```

You can provide multiple placements to customize multiple bars at once, as in the following example:

```swift
TabView {
    NavigationView {
        ContentView()
            .toolbarBackgroundVisibility(
                .visible, for: .navigationBar, .tabBar)
    }
}
```

## Setting toolbar visibility

- **toolbar(_:for:)**: Specifies the visibility of a bar managed by SwiftUI.
- **toolbarVisibility(_:for:)**: Specifies the visibility of a bar managed by SwiftUI.
- **ToolbarPlacement**: The placement of a toolbar.
- **ContentToolbarPlacement**

