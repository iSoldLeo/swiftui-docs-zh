--- 来源：https://developer.apple.com/documentation/SwiftUI/SearchFieldPlacement/navigationBarDrawer
抓取时间：2025-12-03T06:05:24Z

---

# navigationBarDrawer

**类型属性**

搜索框显示在导航栏中。

## 声明

```swift
static let navigationBarDrawer: SearchFieldPlacement
```

## 讨论

搜索框显示在任何导航栏标题下方，并使用 [automatic](NavigationBarDrawerDisplayMode/automatic.zh-Hans.md) 显示模式来配置何时隐藏搜索框。要选择其他显示模式，请改用 [navigationBarDrawer(displayMode:)](navigationBarDrawer_displayMode.zh-Hans.md)。

## 获取搜索框位置

- **automatic**：SwiftUI 会自动放置搜索框。

- **navigationBarDrawer(displayMode:)**：搜索框使用指定的显示模式显示在导航栏中。

- **sidebar**：搜索框显示在导航视图的侧边栏中。

- **toolbar**：搜索框显示在工具栏中。


---
source: https://developer.apple.com/documentation/SwiftUI/SearchFieldPlacement/navigationBarDrawer
crawled: 2025-12-03T06:05:24Z
---

# navigationBarDrawer

**Type Property**

The search field appears in the navigation bar.

## Declaration

```swift
static let navigationBarDrawer: SearchFieldPlacement
```

## Discussion

The field appears below any navigation bar title and uses the [automatic](NavigationBarDrawerDisplayMode/automatic.zh-Hans.md) display mode to configure when to hide the search field. To choose a different display mode, use [navigationBarDrawer(displayMode:)](navigationBarDrawer_displayMode.zh-Hans.md) instead.

## Getting a search field placement

- **automatic**: SwiftUI places the search field automatically.
- **navigationBarDrawer(displayMode:)**: The search field appears in the navigation bar using the specified display mode.
- **sidebar**: The search field appears in the sidebar of a navigation view.
- **toolbar**: The search field appears in the toolbar.

