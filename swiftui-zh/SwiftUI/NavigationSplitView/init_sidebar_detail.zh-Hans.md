---
来源：https://developer.apple.com/documentation/SwiftUI/NavigationSplitView/init(侧边栏:detail:)
抓取时间：2025-12-02T20:58:33Z
---

# init(sidebar:detail:)

**Initializer**

创建双栏导航分割视图。

## 声明

```swift
init(@ViewBuilder sidebar: () -> Sidebar, @ViewBuilder detail: () -> Detail) where Content == EmptyView
```

## 参数

- **sidebar**：要在前导列中显示的视图。
- **detail**：在详细区域中显示的视图。

## 创建导航分割视图

- **init(sidebar:content:detail:)**：创建三栏导航分割视图。


---
source: https://developer.apple.com/documentation/SwiftUI/NavigationSplitView/init(sidebar:detail:)
crawled: 2025-12-02T20:58:33Z
---

# init(sidebar:detail:)

**Initializer**

Creates a two-column navigation split view.

## Declaration

```swift
init(@ViewBuilder sidebar: () -> Sidebar, @ViewBuilder detail: () -> Detail) where Content == EmptyView
```

## Parameters

- **sidebar**: The view to show in the leading column.
- **detail**: The view to show in the detail area.

## Creating a navigation split view

- **init(sidebar:content:detail:)**: Creates a three-column navigation split view.

