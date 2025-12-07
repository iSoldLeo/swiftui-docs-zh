--- 来源：https://developer.apple.com/documentation/SwiftUI/SearchFieldPlacement/automatic
抓取时间：2025-12-03T06:05:23Z

---

# automatic

**Type 属性**

SwiftUI 会自动放置搜索框。

## 声明

```swift
static let automatic: SearchFieldPlacement
```

## 讨论

搜索框的位置取决于平台：

- 在 iOS、iPadOS 和 macOS 中，搜索框显示在工具栏中。

- 在 tvOS 和 watchOS 中，搜索框与内容内嵌显示。

## 获取搜索框位置

- **navigationBarDrawer**：搜索框显示在导航栏中。

- **navigationBarDrawer(displayMode:)**：搜索框以指定的显示模式显示在导航栏中。

- **sidebar**：搜索框显示在导航视图的侧边栏中。

- **toolbar**：搜索框显示在工具栏中。


---
source: https://developer.apple.com/documentation/SwiftUI/SearchFieldPlacement/automatic
crawled: 2025-12-03T06:05:23Z
---

# automatic

**Type Property**

SwiftUI places the search field automatically.

## Declaration

```swift
static let automatic: SearchFieldPlacement
```

## Discussion

Placement of the search field depends on the platform:

- In iOS, iPadOS, and macOS, the search field appears in the toolbar.
- In tvOS and watchOS, the search field appears inline with its content.

## Getting a search field placement

- **navigationBarDrawer**: The search field appears in the navigation bar.
- **navigationBarDrawer(displayMode:)**: The search field appears in the navigation bar using the specified display mode.
- **sidebar**: The search field appears in the sidebar of a navigation view.
- **toolbar**: The search field appears in the toolbar.

