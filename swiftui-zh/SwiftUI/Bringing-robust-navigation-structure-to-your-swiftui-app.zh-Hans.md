---
来源： https://developer.apple.com/documentation/SwiftUI/Bringing-robust-navigation-structure-to-your-swiftui-app
抓取时间： 2025-12-02T15:50:54Z
---

# 为 SwiftUI 应用程序带来强大的导航结构

**示例代码**

使用导航链接、堆栈、目的地和路径为所有平台提供简化的体验，以及深度链接和状态恢复等行为。

## 概览



##以列的形式呈现视图

- 迁移到新的导航类型**：用导航堆栈和导航分割视图取代导航视图，改进应用程序中的导航行为。
- **NavigationSplitView**：以两列或三列形式显示视图的视图，其中前列的选择可控制后列的显示。
- **navigationSplitViewStyle(_:)**：设置该视图中导航分割视图的样式。
- **navigationSplitViewColumnWidth(_:)**：为包含此视图的列设置固定的首选宽度。
- **navigationSplitViewColumnWidth(min:ideal:max:)**：为包含此视图的列设置灵活的首选宽度。
- **NavigationSplitViewVisibility**：导航分割视图中前导列的可见性。
- **NavigationLink**：控制导航显示的视图。


---
source: https://developer.apple.com/documentation/SwiftUI/Bringing-robust-navigation-structure-to-your-swiftui-app
crawled: 2025-12-02T15:50:54Z
---

# Bringing robust navigation structure to your SwiftUI app

**Sample Code**

Use navigation links, stacks, destinations, and paths to provide a streamlined experience for all platforms, as well as behaviors such as deep linking and state restoration.

## Overview



## Presenting views in columns

- **Migrating to new navigation types**: Improve navigation behavior in your app by replacing navigation views with navigation stacks and navigation split views.
- **NavigationSplitView**: A view that presents views in two or three columns, where selections in leading columns control presentations in subsequent columns.
- **navigationSplitViewStyle(_:)**: Sets the style for navigation split views within this view.
- **navigationSplitViewColumnWidth(_:)**: Sets a fixed, preferred width for the column containing this view.
- **navigationSplitViewColumnWidth(min:ideal:max:)**: Sets a flexible, preferred width for the column containing this view.
- **NavigationSplitViewVisibility**: The visibility of the leading columns in a navigation split view.
- **NavigationLink**: A view that controls a navigation presentation.

