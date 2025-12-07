--- 来源：https://developer.apple.com/documentation/SwiftUI/SearchFieldPlacement/toolbar
抓取时间：2025-12-03T06:05:26Z

---

# 工具栏

**类型属性**

搜索框显示在工具栏中。

## 声明

```swift
static let toolbar: SearchFieldPlacement
```

## 讨论

搜索框的具体位置取决于平台：

- 在 iOS 和 watchOS 中，搜索框显示在导航栏下方，滚动即可显示。

- 在 iPadOS 中，搜索框显示在导航栏的末尾。

- 在 macOS 中，搜索框显示在工具栏的末尾。

## 获取搜索框位置

- **automatic**：SwiftUI 会自动放置搜索框。

- **navigationBarDrawer**：搜索框显示在导航栏中。

- **navigationBarDrawer(displayMode:)**：搜索框将以指定的显示模式显示在导航栏中。

- **sidebar**：搜索框将显示在导航视图的侧边栏中。


---
source: https://developer.apple.com/documentation/SwiftUI/SearchFieldPlacement/toolbar
crawled: 2025-12-03T06:05:26Z
---

# toolbar

**Type Property**

The search field appears in the toolbar.

## Declaration

```swift
static let toolbar: SearchFieldPlacement
```

## Discussion

The precise placement depends on the platform:

- In iOS and watchOS, the search field appears below the navigation bar and is revealed by scrolling.
- In iPadOS, the search field appears in the trailing navigation bar.
- In macOS, the search field appears in the trailing toolbar.

## Getting a search field placement

- **automatic**: SwiftUI places the search field automatically.
- **navigationBarDrawer**: The search field appears in the navigation bar.
- **navigationBarDrawer(displayMode:)**: The search field appears in the navigation bar using the specified display mode.
- **sidebar**: The search field appears in the sidebar of a navigation view.

