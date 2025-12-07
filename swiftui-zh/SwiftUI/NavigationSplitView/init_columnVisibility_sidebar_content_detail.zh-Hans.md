---
来源：https://developer.apple.com/documentation/SwiftUI/NavigationSplitView/init(columnVisibility:sidebar:content:detail:)
抓取时间：2025-12-02T20:58:35Z
---

# init(columnVisibility:sidebar:content:detail:)

**Initializer**

创建三栏导航分割视图，可对前导栏的可见性进行编程控制。

### 声明

```swift
init(columnVisibility: Binding<NavigationSplitViewVisibility>, @ViewBuilder sidebar: () -> Sidebar, @ViewBuilder content: () -> Content, @ViewBuilder detail: () -> Detail)
```

## 参数

- **columnVisibility**：一个 [Binding](../Binding.zh-Hans.md) 状态，用于控制前导列的可见性。
- **sidebar**：在前导列中显示的视图。
- **content**：在中间栏显示的视图。
- **detail**：在详细区域中显示的视图。

## 在导航分割视图中隐藏列

- **init(columnVisibility:sidebar:detail:)**：创建一个双列导航分割视图，可对侧边栏的可见性进行编程控制。


---
source: https://developer.apple.com/documentation/SwiftUI/NavigationSplitView/init(columnVisibility:sidebar:content:detail:)
crawled: 2025-12-02T20:58:35Z
---

# init(columnVisibility:sidebar:content:detail:)

**Initializer**

Creates a three-column navigation split view that enables programmatic control of leading columns’ visibility.

## Declaration

```swift
init(columnVisibility: Binding<NavigationSplitViewVisibility>, @ViewBuilder sidebar: () -> Sidebar, @ViewBuilder content: () -> Content, @ViewBuilder detail: () -> Detail)
```

## Parameters

- **columnVisibility**: A [Binding](../Binding.zh-Hans.md) to state that controls the visibility of the leading columns.
- **sidebar**: The view to show in the leading column.
- **content**: The view to show in the middle column.
- **detail**: The view to show in the detail area.

## Hiding columns in a navigation split view

- **init(columnVisibility:sidebar:detail:)**: Creates a two-column navigation split view that enables programmatic control of the sidebar’s visibility.

