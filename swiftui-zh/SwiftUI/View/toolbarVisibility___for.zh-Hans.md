--- 来源：https://developer.apple.com/documentation/swiftui/view/toolbarvisibility(_:for:)

抓取时间：2025-12-02T16:16:11Z

---

# toolbarVisibility(_:for:)

**实例方法**

指定由 SwiftUI 管理的工具栏的可见性。

## 声明

```swift
nonisolated func toolbarVisibility(_ visibility: Visibility, for bars: ToolbarPlacement...) -> some View

```

## 参数

- **visibility**：工具栏的首选可见性。

- **bars**：要更新可见性的工具栏列表；如果为空，则为 [automatic](../ToolbarPlacement/automatic.zh-Hans.md)。

## 说明

首选可见性会传递给渲染工具栏的最近的容器。在 iOS 中，这可能是 [NavigationView](../NavigationView.zh-Hans.md) 或 [TabView](../TabView.zh-Hans.md)，在 macOS 中，这可能是 [WindowGroup](../WindowGroup.zh-Hans.md) 的根视图。

此示例展示了一个隐藏 iOS 导航栏或 macOS 窗口工具栏项目的视图。

```swift
NavigationView {
    ContentView()
        .toolbarVisibility(.hidden)
}
```

要在 macOS 上隐藏整个标题栏，请将此修饰符与 [windowToolbar](../ToolbarPlacement/windowToolbar.zh-Hans.md) 位置一起使用。

```swift
NavigationView {
    ContentView()
        .toolbarVisibility(.hidden, for: .windowToolbar)
}
```

您可以提供多个 [ToolbarPlacement](../ToolbarPlacement.zh-Hans.md) 实例来同时隐藏多个栏。

```swift
TabView {
    NavigationView {
        ContentView()
            .toolbarVisibility(
                .hidden, for: .navigationBar, .tabBar)
    }
}
```

根据指定的栏，可能无法满足请求的可见性要求。

## 设置工具栏可见性

- **toolbar(_:for:)**：指定由 SwiftUI 管理的工具栏的可见性。

- **toolbarBackgroundVisibility(_:for:)**：指定由 SwiftUI 管理的工具栏上背景的首选可见性。

- **ToolbarPlacement**：工具栏的位置。

- **ContentToolbarPlacement**


---
source: https://developer.apple.com/documentation/swiftui/view/toolbarvisibility(_:for:)
crawled: 2025-12-02T16:16:11Z
---

# toolbarVisibility(_:for:)

**Instance Method**

Specifies the visibility of a bar managed by SwiftUI.

## Declaration

```swift
nonisolated func toolbarVisibility(_ visibility: Visibility, for bars: ToolbarPlacement...) -> some View

```

## Parameters

- **visibility**: The preferred visibility of the bar.
- **bars**: The bars to update the visibility of or [automatic](../ToolbarPlacement/automatic.zh-Hans.md) if empty.

## Discussion

The preferred visibility flows up to the nearest container that renders a bar. This could be a [NavigationView](../NavigationView.zh-Hans.md) or [TabView](../TabView.zh-Hans.md) in iOS, or the root view of a [WindowGroup](../WindowGroup.zh-Hans.md) in macOS.

This examples shows a view that hides the navigation bar on iOS, or the window toolbar items on macOS.

```swift
NavigationView {
    ContentView()
        .toolbarVisibility(.hidden)
}
```

To hide the entire titlebar on macOS, use this modifier with [windowToolbar](../ToolbarPlacement/windowToolbar.zh-Hans.md) placement.

```swift
NavigationView {
    ContentView()
        .toolbarVisibility(.hidden, for: .windowToolbar)
}
```

You can provide multiple [ToolbarPlacement](../ToolbarPlacement.zh-Hans.md) instances to hide multiple bars at once.

```swift
TabView {
    NavigationView {
        ContentView()
            .toolbarVisibility(
                .hidden, for: .navigationBar, .tabBar)
    }
}
```



Depending on the specified bars, the requested visibility may not be able to be fulfilled.

## Setting toolbar visibility

- **toolbar(_:for:)**: Specifies the visibility of a bar managed by SwiftUI.
- **toolbarBackgroundVisibility(_:for:)**: Specifies the preferred visibility of backgrounds on a bar managed by SwiftUI.
- **ToolbarPlacement**: The placement of a toolbar.
- **ContentToolbarPlacement**

