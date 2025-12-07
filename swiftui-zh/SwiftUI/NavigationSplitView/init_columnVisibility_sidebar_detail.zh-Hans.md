---
来源： https://developer.apple.com/documentation/SwiftUI/NavigationSplitView/init(columnVisibility:sidebar:detail:)
抓取时间：2025-12-01T00:42:40Z


# init(columnVisibility:sidebar:detail:)

**Initializer**

创建双栏导航分割视图，可对边栏的可见性进行编程控制。

### 声明

```swift
init(columnVisibility: Binding<NavigationSplitViewVisibility>, @ViewBuilder sidebar: () -> Sidebar, @ViewBuilder detail: () -> Detail) where Content == EmptyView
```

## 参数

- **columnVisibility**：一个 [Binding](../Binding.zh-Hans.md) 状态，用于控制前导列的可见性。
- **sidebar**：在引导列中显示的视图。
- **detail**：在详细区域中显示的视图。

## 在导航分割视图中隐藏列

- **init(columnVisibility:sidebar:content:detail:)**：创建一个三列导航分割视图，该视图可对前导列的可见性进行编程控制。


---
source: https://developer.apple.com/documentation/SwiftUI/NavigationSplitView/init(columnVisibility:sidebar:detail:)
crawled: 2025-12-01T00:42:40Z
---

# init(columnVisibility:sidebar:detail:)

**Initializer**

Creates a two-column navigation split view that enables programmatic control of the sidebar’s visibility.

## Declaration

```swift
init(columnVisibility: Binding<NavigationSplitViewVisibility>, @ViewBuilder sidebar: () -> Sidebar, @ViewBuilder detail: () -> Detail) where Content == EmptyView
```

## Parameters

- **columnVisibility**: A [Binding](../Binding.zh-Hans.md) to state that controls the visibility of the leading column.
- **sidebar**: The view to show in the leading column.
- **detail**: The view to show in the detail area.

## Hiding columns in a navigation split view

- **init(columnVisibility:sidebar:content:detail:)**: Creates a three-column navigation split view that enables programmatic control of leading columns’ visibility.

