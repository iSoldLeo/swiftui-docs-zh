---
来源：https://developer.apple.com/documentation/SwiftUI/NavigationSplitView/init(columnVisibility:preferredCompactColumn:sidebar:detail:)
抓取时间：2025-12-02T20:58:37Z
---

# init(columnVisibility:preferredCompactColumn:sidebar:detail:)

**Initializer**

创建一个双列导航分割视图，该视图可通过编程控制边栏在常规尺寸下的可见性，以及在窄尺寸下视图折叠为单列时哪一列显示在顶部。

### 声明

```swift
nonisolated init(columnVisibility: Binding<NavigationSplitViewVisibility>, preferredCompactColumn: Binding<NavigationSplitViewColumn>, @ViewBuilder sidebar: () -> Sidebar, @ViewBuilder detail: () -> Detail) where Content == EmptyView
```

## 参数

- **columnVisibility**：一个 [Binding](../Binding.zh-Hans.md) 状态，用于控制前导列的可见性。
- **preferredCompactColumn**：[Binding](../Binding.zh-Hans.md)，用于在视图折叠时控制哪一列显示在顶部。
- **sidebar**：在前导列中显示的视图。
- **detail**：在详细区域中显示的视图。

## 指定首选紧凑列和列可见性

- **init(columnVisibility:preferredCompactColumn:sidebar:content:detail:)**：创建三列导航分割视图，可对常规尺寸下的前导列可见性以及窄尺寸下视图折叠为单列时显示在顶部的列进行编程控制。


---
source: https://developer.apple.com/documentation/SwiftUI/NavigationSplitView/init(columnVisibility:preferredCompactColumn:sidebar:detail:)
crawled: 2025-12-02T20:58:37Z
---

# init(columnVisibility:preferredCompactColumn:sidebar:detail:)

**Initializer**

Creates a two-column navigation split view that enables programmatic control of the sidebar’s visibility in regular sizes and which column appears on top when the view collapses into a single column in narrow sizes.

## Declaration

```swift
nonisolated init(columnVisibility: Binding<NavigationSplitViewVisibility>, preferredCompactColumn: Binding<NavigationSplitViewColumn>, @ViewBuilder sidebar: () -> Sidebar, @ViewBuilder detail: () -> Detail) where Content == EmptyView
```

## Parameters

- **columnVisibility**: A [Binding](../Binding.zh-Hans.md) to state that controls the visibility of the leading column.
- **preferredCompactColumn**: A [Binding](../Binding.zh-Hans.md) to state that controls which column appears on top when the view collapses.
- **sidebar**: The view to show in the leading column.
- **detail**: The view to show in the detail area.

## Specifying a preferred compact column and column visibility

- **init(columnVisibility:preferredCompactColumn:sidebar:content:detail:)**: Creates a three-column navigation split view that enables programmatic control of leading columns’ visibility in regular sizes and which column appears on top when the view collapses into a single column in narrow sizes.

