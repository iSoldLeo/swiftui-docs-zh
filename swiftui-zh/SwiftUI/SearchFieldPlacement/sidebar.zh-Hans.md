--- 来源：https://developer.apple.com/documentation/SwiftUI/SearchFieldPlacement/sidebar
抓取时间：2025-12-03T06:05:25Z

---

# 侧边栏

**类型属性**

搜索框显示在导航视图的侧边栏中。

## 声明

```swift
static var sidebar: SearchFieldPlacement { get }
```

## 讨论

搜索框的具体位置取决于平台：

- 在 iOS 和 iPadOS 中，搜索框显示在与侧边栏关联的导航栏部分。

- 在 macOS 中，搜索框以固定标题的形式显示在侧边栏中，并附加到工具栏。

如果侧边栏不可用（例如，当您将可搜索修饰符应用于导航拆分视图以外的视图时），SwiftUI 会使用自动定位。

## 获取搜索框位置

- **automatic**：SwiftUI 会自动放置搜索框。

- **navigationBarDrawer**：搜索框显示在导航栏中。

- **navigationBarDrawer(displayMode:)**：搜索框以指定的显示模式显示在导航栏中。

- **toolbar**：搜索框显示在工具栏中。


---
source: https://developer.apple.com/documentation/SwiftUI/SearchFieldPlacement/sidebar
crawled: 2025-12-03T06:05:25Z
---

# sidebar

**Type Property**

The search field appears in the sidebar of a navigation view.

## Declaration

```swift
static var sidebar: SearchFieldPlacement { get }
```

## Discussion

The precise placement depends on the platform:

- In iOS and iPadOS the search field appears in the section of the navigation bar associated with the sidebar.
- In macOS the search field appears as a sticky header in the sidebar, attached to the toolbar.

If a sidebar isn’t available, like when you apply the searchable modifier to a view other than a navigation split view, SwiftUI uses automatic placement instead.



## Getting a search field placement

- **automatic**: SwiftUI places the search field automatically.
- **navigationBarDrawer**: The search field appears in the navigation bar.
- **navigationBarDrawer(displayMode:)**: The search field appears in the navigation bar using the specified display mode.
- **toolbar**: The search field appears in the toolbar.

