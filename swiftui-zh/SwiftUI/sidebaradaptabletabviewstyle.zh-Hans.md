--- 来源：https://developer.apple.com/documentation/swiftui/sidebaradaptabletabviewstyle
抓取时间：2025-12-05T22:21:17Z

---

# SidebarAdaptableTabViewStyle

**Structure**

一种可适应不同平台的标签栏样式。

## 声明

```swift
struct SidebarAdaptableTabViewStyle
```

## 概述

使用 SidebarAdaptableTabViewStyle 的标签视图外观会因平台而异：

- iPadOS 显示顶部标签栏，该标签栏可转换为侧边栏。

- iOS 显示底部标签栏。

- macOS 和 tvOS 始终显示侧边栏。

- VisionOS 显示装饰效果，并在 [TabSection](TabSection.zh-Hans.md) 内显示辅助标签的侧边栏。

使用 [sidebarAdaptable](TabViewStyle/sidebarAdaptable.zh-Hans.md) 构造此样式。

要将此样式应用于选项卡视图或包含选项卡视图的视图，请使用 [tabViewStyle(_:)](View/tabViewStyle.zh-Hans.md) 修饰符。

## 初始化器

- **init()**

## 支持的类型

- **DefaultTabViewStyle**：默认的选项卡视图样式。

- **TabBarOnlyTabViewStyle**：尽可能显示选项卡栏的选项卡视图样式。

- **GroupedTabViewStyle**：显示选项卡栏并将选项卡分组在一起的选项卡视图样式。

- **PageTabViewStyle**：显示分页滚动 `TabView` 的 `TabViewStyle`。

- **VerticalPageTabViewStyle**：一个用于显示垂直 `TabView` 交互和外观的 `TabViewStyle`。

- **CarouselTabViewStyle**：一个实现轮播图交互和外观的样式。

## 符合以下规范

- TabViewStyle


---
source: https://developer.apple.com/documentation/swiftui/sidebaradaptabletabviewstyle
crawled: 2025-12-05T22:21:17Z
---

# SidebarAdaptableTabViewStyle

**Structure**

A tab bar style that adapts to each platform.

## Declaration

```swift
struct SidebarAdaptableTabViewStyle
```

## Overview

Tab views using the sidebar adaptable style have an appearance that varies depending on the platform:

- iPadOS displays a top tab bar that can adapt into a sidebar.
- iOS displays a bottom tab bar.
- macOS and tvOS always show a sidebar.
- visionOS shows an ornament and also shows a sidebar for secondary tabs within a [TabSection](TabSection.zh-Hans.md).

Use [sidebarAdaptable](TabViewStyle/sidebarAdaptable.zh-Hans.md) to construct this style.

To apply this style to a tab view, or to a view that contains tab views, use the [tabViewStyle(_:)](View/tabViewStyle.zh-Hans.md) modifier.

## Initializers

- **init()**

## Supporting types

- **DefaultTabViewStyle**: The default tab view style.
- **TabBarOnlyTabViewStyle**: A tab view style that displays a tab bar when possible.
- **GroupedTabViewStyle**: A tab view style that displays a tab bar that groups its tabs together.
- **PageTabViewStyle**: A `TabViewStyle` that displays a paged scrolling `TabView`.
- **VerticalPageTabViewStyle**: A `TabViewStyle` that displays a vertical `TabView` interaction and appearance.
- **CarouselTabViewStyle**: A style that implements the carousel interaction and appearance.

## Conforms To

- TabViewStyle

