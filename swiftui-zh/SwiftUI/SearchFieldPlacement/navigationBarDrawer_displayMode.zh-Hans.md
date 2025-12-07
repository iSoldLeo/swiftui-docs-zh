--- 来源：https://developer.apple.com/documentation/SwiftUI/SearchFieldPlacement/navigationBarDrawer(displayMode:)

抓取时间：2025-12-01T10:54:26Z

---

# navigationBarDrawer(displayMode:)

**类型方法**

搜索框将以指定的显示模式显示在导航栏中。

## 声明

```swift
static func navigationBarDrawer(displayMode: SearchFieldPlacement.NavigationBarDrawerDisplayMode) -> SearchFieldPlacement
```

## 参数

- **displayMode**：一个控件，用于指示是否在滚动时隐藏搜索框。

## 说明

搜索框将显示在任何导航栏标题下方。系统可以根据您设置的 `displayMode` 在滚动时隐藏搜索框。

## 获取搜索框位置

- **automatic**：SwiftUI 会自动放置搜索框。

- **navigationBarDrawer**：搜索框显示在导航栏中。

- **sidebar**：搜索框显示在导航视图的侧边栏中。

- **toolbar**：搜索框显示在工具栏中。


---
source: https://developer.apple.com/documentation/SwiftUI/SearchFieldPlacement/navigationBarDrawer(displayMode:)
crawled: 2025-12-01T10:54:26Z
---

# navigationBarDrawer(displayMode:)

**Type Method**

The search field appears in the navigation bar using the specified display mode.

## Declaration

```swift
static func navigationBarDrawer(displayMode: SearchFieldPlacement.NavigationBarDrawerDisplayMode) -> SearchFieldPlacement
```

## Parameters

- **displayMode**: A control that indicates whether to hide the search field in response to scrolling.

## Discussion

The field appears below any navigation bar title. The system can hide the field in response to scrolling, depending on the `displayMode` that you set.

## Getting a search field placement

- **automatic**: SwiftUI places the search field automatically.
- **navigationBarDrawer**: The search field appears in the navigation bar.
- **sidebar**: The search field appears in the sidebar of a navigation view.
- **toolbar**: The search field appears in the toolbar.

