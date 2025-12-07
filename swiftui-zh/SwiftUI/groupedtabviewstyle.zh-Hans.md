---
来源： https://developer.apple.com/documentation/swiftui/groupedtabviewstyle
抓取时间： 2025-12-05T22:21:19Z
---

# GroupedTabViewStyle

**Structure**

一种标签视图样式，用于显示将标签分组的标签栏。

## 声明

```swift
struct GroupedTabViewStyle
```

## 概览

使用 [grouped](TabViewStyle/grouped.zh-Hans.md) 构建此样式。

要将此样式应用于选项卡视图或包含选项卡视图的视图，请使用 [tabViewStyle(_:)](View/tabViewStyle.zh-Hans.md) 修饰符。

## 初始化器

- **init()**

## 支持类型

- **DefaultTabViewStyle**：默认选项卡视图样式。
- **SidebarAdaptableTabViewStyle**：适应每个平台的标签栏样式。
- **TabBarOnlyTabViewStyle**：在可能的情况下显示选项卡栏的选项卡视图样式。
- **PageTabViewStyle**：显示分页滚动⟦的`TabViewStyle`。
- **VerticalPageTabViewStyle**：显示垂直`TabViewStyle` 互动和外观的`TabView`。
- **CarouselTabViewStyle**：实现旋转木马交互和外观的样式。

## 符合

- TabViewStyle


---
source: https://developer.apple.com/documentation/swiftui/groupedtabviewstyle
crawled: 2025-12-05T22:21:19Z
---

# GroupedTabViewStyle

**Structure**

A tab view style that displays a tab bar that groups its tabs together.

## Declaration

```swift
struct GroupedTabViewStyle
```

## Overview

Use [grouped](TabViewStyle/grouped.zh-Hans.md) to construct this style.

To apply this style to a tab view, or to a view that contains tab views, use the [tabViewStyle(_:)](View/tabViewStyle.zh-Hans.md) modifier.

## Initializers

- **init()**

## Supporting types

- **DefaultTabViewStyle**: The default tab view style.
- **SidebarAdaptableTabViewStyle**: A tab bar style that adapts to each platform.
- **TabBarOnlyTabViewStyle**: A tab view style that displays a tab bar when possible.
- **PageTabViewStyle**: A `TabViewStyle` that displays a paged scrolling `TabView`.
- **VerticalPageTabViewStyle**: A `TabViewStyle` that displays a vertical `TabView` interaction and appearance.
- **CarouselTabViewStyle**: A style that implements the carousel interaction and appearance.

## Conforms To

- TabViewStyle

