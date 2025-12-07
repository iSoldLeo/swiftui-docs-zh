---
来源：https://developer.apple.com/documentation/SwiftUI/NavigationSplitView/init(columnVisibility:preferredCompactColumn:sidebar:content:detail:)
抓取时间： 2025-12-01T00:42:43Z
---

# init(columnVisibility:preferredCompactColumn:sidebar:content:detail:)

**Initializer**

创建一个三列导航分割视图，该视图可通过编程控制常规尺寸下前导列的可见性，以及在窄尺寸下视图折叠为单列时哪一列显示在顶部。

### 声明

```swift
nonisolated init(columnVisibility: Binding<NavigationSplitViewVisibility>, preferredCompactColumn: Binding<NavigationSplitViewColumn>, @ViewBuilder sidebar: () -> Sidebar, @ViewBuilder content: () -> Content, @ViewBuilder detail: () -> Detail)
```

## 参数

- **columnVisibility**：一个 [Binding](../Binding.zh-Hans.md) 状态，用于控制前导列的可见性。
- **preferredCompactColumn**：[Binding](../Binding.zh-Hans.md)，用于控制视图折叠时哪一列显示在顶部。
- **sidebar**：在前导列中显示的视图。
- **content**：在中间栏显示的视图。
- **detail**：在详细区域中显示的视图。

## 指定首选紧凑列和列可见性

- **init(columnVisibility:preferredCompactColumn:sidebar:detail:)**：创建双列导航分割视图，可对常规尺寸下边栏的可见性进行编程控制，以及在窄尺寸下视图折叠为单列时哪一列显示在顶部。


---
source: https://developer.apple.com/documentation/SwiftUI/NavigationSplitView/init(columnVisibility:preferredCompactColumn:sidebar:content:detail:)
crawled: 2025-12-01T00:42:43Z
---

# init(columnVisibility:preferredCompactColumn:sidebar:content:detail:)

**Initializer**

Creates a three-column navigation split view that enables programmatic control of leading columns’ visibility in regular sizes and which column appears on top when the view collapses into a single column in narrow sizes.

## Declaration

```swift
nonisolated init(columnVisibility: Binding<NavigationSplitViewVisibility>, preferredCompactColumn: Binding<NavigationSplitViewColumn>, @ViewBuilder sidebar: () -> Sidebar, @ViewBuilder content: () -> Content, @ViewBuilder detail: () -> Detail)
```

## Parameters

- **columnVisibility**: A [Binding](../Binding.zh-Hans.md) to state that controls the visibility of the leading columns.
- **preferredCompactColumn**: A [Binding](../Binding.zh-Hans.md) to state that controls which column appears on top when the view collapses.
- **sidebar**: The view to show in the leading column.
- **content**: The view to show in the middle column.
- **detail**: The view to show in the detail area.

## Specifying a preferred compact column and column visibility

- **init(columnVisibility:preferredCompactColumn:sidebar:detail:)**: Creates a two-column navigation split view that enables programmatic control of the sidebar’s visibility in regular sizes and which column appears on top when the view collapses into a single column in narrow sizes.

