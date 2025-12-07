--- 来源：https://developer.apple.com/documentation/swiftui/tabbaronlytabviewstyle
抓取时间：2025-12-05T22:21:18Z

---

# TabBarOnlyTabViewStyle

**Structure**

一种尽可能显示标签栏的标签视图样式。

## 声明

```swift
struct TabBarOnlyTabViewStyle
```

## 概述

使用 [tabBarOnly](TabViewStyle/tabBarOnly.zh-Hans.md) 构造此样式。

要将此样式应用于标签视图或包含标签视图的视图，请使用 [tabViewStyle(_:)](View/tabViewStyle.zh-Hans.md) 修饰符。

## 初始化器

- **init()**

## 支持的类型

- **DefaultTabViewStyle**：默认的标签视图样式。

- **SidebarAdaptableTabViewStyle**：一种可适应各个平台的标签栏样式。

- **GroupedTabViewStyle**：一种标签视图样式，显示一个将标签分组在一起的标签栏。

- **PageTabViewStyle**：一种 `TabViewStyle`，显示分页滚动 `TabView`。

- **VerticalPageTabViewStyle**：一种 `TabViewStyle`，显示垂直 `TabView` 交互和外观。

- **CarouselTabViewStyle**：一种实现轮播交互和外观的样式。

## 符合以下规范

- TabViewStyle


---
source: https://developer.apple.com/documentation/swiftui/tabbaronlytabviewstyle
crawled: 2025-12-05T22:21:18Z
---

# TabBarOnlyTabViewStyle

**Structure**

A tab view style that displays a tab bar when possible.

## Declaration

```swift
struct TabBarOnlyTabViewStyle
```

## Overview

Use [tabBarOnly](TabViewStyle/tabBarOnly.zh-Hans.md) to construct this style.

To apply this style to a tab view, or to a view that contains tab views, use the [tabViewStyle(_:)](View/tabViewStyle.zh-Hans.md) modifier.

## Initializers

- **init()**

## Supporting types

- **DefaultTabViewStyle**: The default tab view style.
- **SidebarAdaptableTabViewStyle**: A tab bar style that adapts to each platform.
- **GroupedTabViewStyle**: A tab view style that displays a tab bar that groups its tabs together.
- **PageTabViewStyle**: A `TabViewStyle` that displays a paged scrolling `TabView`.
- **VerticalPageTabViewStyle**: A `TabViewStyle` that displays a vertical `TabView` interaction and appearance.
- **CarouselTabViewStyle**: A style that implements the carousel interaction and appearance.

## Conforms To

- TabViewStyle

