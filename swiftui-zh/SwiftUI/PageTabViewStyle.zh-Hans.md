---
来源： https://developer.apple.com/documentation/SwiftUI/PageTabViewStyle
抓取时间： 2025-12-03T06:11:25Z
---

# PageTabViewStyle

**Structure**

显示分页滚动`TabViewStyle`的`TabView`。

## 声明

```swift
struct PageTabViewStyle
```

## 概览

使用 [page](TabViewStyle/page.zh-Hans.md) 或 [page(indexDisplayMode:)](TabViewStyle/page_indexDisplayMode.zh-Hans.md) 构建此样式。

要将此样式应用于选项卡视图或包含选项卡视图的视图，请使用 [tabViewStyle(_:)](View/tabViewStyle.zh-Hans.md) 修饰符。

## 创建页面标签视图样式

- **init(indexDisplayMode:)**：创建具有索引显示模式的新 `PageTabViewStyle`
- **PageTabViewStyle.IndexDisplayMode**：用于显示页面索引视图的样式

## 支持类型

- **DefaultTabViewStyle**：默认选项卡视图样式。
- **SidebarAdaptableTabViewStyle**：适应每个平台的标签栏样式。
- **TabBarOnlyTabViewStyle**：在可能的情况下显示选项卡栏的选项卡视图样式。
- **GroupedTabViewStyle**：一种选项卡视图样式，可显示将选项卡分组在一起的选项卡栏。
- **VerticalPageTabViewStyle**：显示垂直`TabViewStyle`交互和外观的`TabView`。
- **CarouselTabViewStyle**：实现旋转木马交互和外观的样式。

## 符合

- TabViewStyle


---
source: https://developer.apple.com/documentation/SwiftUI/PageTabViewStyle
crawled: 2025-12-03T06:11:25Z
---

# PageTabViewStyle

**Structure**

A `TabViewStyle` that displays a paged scrolling `TabView`.

## Declaration

```swift
struct PageTabViewStyle
```

## Overview

Use [page](TabViewStyle/page.zh-Hans.md) or [page(indexDisplayMode:)](TabViewStyle/page_indexDisplayMode.zh-Hans.md) to construct this style.

To apply this style to a tab view, or to a view that contains tab views, use the [tabViewStyle(_:)](View/tabViewStyle.zh-Hans.md) modifier.

## Creating a page tab view style

- **init(indexDisplayMode:)**: Creates a new `PageTabViewStyle` with an index display mode
- **PageTabViewStyle.IndexDisplayMode**: A style for displaying the page index view

## Supporting types

- **DefaultTabViewStyle**: The default tab view style.
- **SidebarAdaptableTabViewStyle**: A tab bar style that adapts to each platform.
- **TabBarOnlyTabViewStyle**: A tab view style that displays a tab bar when possible.
- **GroupedTabViewStyle**: A tab view style that displays a tab bar that groups its tabs together.
- **VerticalPageTabViewStyle**: A `TabViewStyle` that displays a vertical `TabView` interaction and appearance.
- **CarouselTabViewStyle**: A style that implements the carousel interaction and appearance.

## Conforms To

- TabViewStyle

