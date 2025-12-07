---
来源： https://developer.apple.com/documentation/SwiftUI/NavigationViewStyle
抓取时间： 2025-12-03T05:43:13Z
---

# 导航视图样式

**Protocol**

导航视图的外观和交互规范。

## 声明

```swift
protocol NavigationViewStyle
```

## 获取内置导航视图样式

- **automatic**：被样式化的视图当前上下文中的默认导航视图样式。
- **columns**：以列为单位的一系列视图所代表的导航视图样式。
- **stack**：由视图堆栈表示的导航视图样式，一次只显示一个顶部视图。

### 支持类型

- **DefaultNavigationViewStyle**：默认导航视图样式。
- **ColumnNavigationViewStyle**：由一系列列视图表示的导航视图样式。
- **StackNavigationViewStyle**：一种导航视图样式，由一次只显示一个顶部视图的视图堆栈表示。
- **DoubleColumnNavigationViewStyle**：由主视图堆栈表示的导航视图样式，可导航到详细视图。

## 导航视图的样式

- **navigationViewStyle(_:)**：设置该视图中导航视图的样式。

## 符合类型

- ColumnNavigationViewStyle
- 默认导航视图样式
- 双列导航视图样式
- 堆栈导航视图样式


---
source: https://developer.apple.com/documentation/SwiftUI/NavigationViewStyle
crawled: 2025-12-03T05:43:13Z
---

# NavigationViewStyle

**Protocol**

A specification for the appearance and interaction of a navigation view.

## Declaration

```swift
protocol NavigationViewStyle
```

## Getting built-in navigation view styles

- **automatic**: The default navigation view style in the current context of the view being styled.
- **columns**: A navigation view style represented by a series of views in columns.
- **stack**: A navigation view style represented by a view stack that only shows a single top view at a time.

## Supporting types

- **DefaultNavigationViewStyle**: The default navigation view style.
- **ColumnNavigationViewStyle**: A navigation view style represented by a series of views in columns.
- **StackNavigationViewStyle**: A navigation view style represented by a view stack that only shows a single top view at a time.
- **DoubleColumnNavigationViewStyle**: A navigation view style represented by a primary view stack that navigates to a detail view.

## Styling navigation views

- **navigationViewStyle(_:)**: Sets the style for navigation views within this view.

## Conforming Types

- ColumnNavigationViewStyle
- DefaultNavigationViewStyle
- DoubleColumnNavigationViewStyle
- StackNavigationViewStyle

