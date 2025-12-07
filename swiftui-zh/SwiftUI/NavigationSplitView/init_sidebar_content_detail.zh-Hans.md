---
来源：https://developer.apple.com/documentation/SwiftUI/NavigationSplitView/init(侧边栏:内容:详情:)
抓取时间： 2025-12-01T00:42:39Z
---

# init(sidebar:content:detail:)

**Initializer**

创建三栏导航分割视图。

## 声明

```swift
init(@ViewBuilder sidebar: () -> Sidebar, @ViewBuilder content: () -> Content, @ViewBuilder detail: () -> Detail)
```

## 参数

- **sidebar**：要在前导列中显示的视图。
- **content**：显示在中间列的视图。
- **detail**：在详细区域中显示的视图。

## 创建导航分割视图

- **init(sidebar:detail:)**：创建双列导航分割视图。


---
source: https://developer.apple.com/documentation/SwiftUI/NavigationSplitView/init(sidebar:content:detail:)
crawled: 2025-12-01T00:42:39Z
---

# init(sidebar:content:detail:)

**Initializer**

Creates a three-column navigation split view.

## Declaration

```swift
init(@ViewBuilder sidebar: () -> Sidebar, @ViewBuilder content: () -> Content, @ViewBuilder detail: () -> Detail)
```

## Parameters

- **sidebar**: The view to show in the leading column.
- **content**: The view to show in the middle column.
- **detail**: The view to show in the detail area.

## Creating a navigation split view

- **init(sidebar:detail:)**: Creates a two-column navigation split view.

