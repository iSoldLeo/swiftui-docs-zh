---
来源： https://developer.apple.com/documentation/SwiftUI/NavigationSplitView/init(preferredCompactColumn:sidebar:detail:)
抓取时间： 2025-12-01T00:42:41Z
---

# init(preferredCompactColumn:sidebar:detail:)

**Initializer**

创建双列导航拆分视图，当视图折叠成窄尺寸的单列时，可通过编程控制哪一列显示在顶部。

### 声明

```swift
nonisolated init(preferredCompactColumn: Binding<NavigationSplitViewColumn>, @ViewBuilder sidebar: () -> Sidebar, @ViewBuilder detail: () -> Detail) where Content == EmptyView
```

## 参数

- **preferredCompactColumn**：一个 [Binding](../Binding.zh-Hans.md) 状态，用于控制视图折叠时哪一列显示在顶部。
- **sidebar**：在前导列中显示的视图。
- **detail**：在详细区域中显示的视图。

## 指定首选紧凑列

- **init(preferredCompactColumn:sidebar:content:detail:)**：创建三列导航拆分视图，当视图折叠成窄尺寸的单列时，可通过编程控制哪一列显示在顶部。


---
source: https://developer.apple.com/documentation/SwiftUI/NavigationSplitView/init(preferredCompactColumn:sidebar:detail:)
crawled: 2025-12-01T00:42:41Z
---

# init(preferredCompactColumn:sidebar:detail:)

**Initializer**

Creates a two-column navigation split view that enables programmatic control over which column appears on top when the view collapses into a single column in narrow sizes.

## Declaration

```swift
nonisolated init(preferredCompactColumn: Binding<NavigationSplitViewColumn>, @ViewBuilder sidebar: () -> Sidebar, @ViewBuilder detail: () -> Detail) where Content == EmptyView
```

## Parameters

- **preferredCompactColumn**: A [Binding](../Binding.zh-Hans.md) to state that controls which column appears on top when the view collapses.
- **sidebar**: The view to show in the leading column.
- **detail**: The view to show in the detail area.

## Specifying a preferred compact column

- **init(preferredCompactColumn:sidebar:content:detail:)**: Creates a three-column navigation split view that enables programmatic control over which column appears on top when the view collapses into a single column in narrow sizes.

