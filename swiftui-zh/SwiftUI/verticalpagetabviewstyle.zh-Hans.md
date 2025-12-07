---
来源： https://developer.apple.com/documentation/swiftui/verticalpagetabviewstyle
抓取时间： 2025-12-05T22:21:23Z
---

# VerticalPageTabViewStyle

**Structure**

显示垂直`TabViewStyle`交互和外观的`TabView`。

## 声明

```swift
struct VerticalPageTabViewStyle
```

## 概览

使用 [verticalPage](TabViewStyle/verticalPage.zh-Hans.md) 构建此样式。

要将此样式应用于选项卡视图或包含选项卡视图的视图，请使用[tabViewStyle(_:)](View/tabViewStyle.zh-Hans.md)修饰符。

## 创建选项卡视图样式

- **init()**
- **init(transitionStyle:)**：创建具有过渡样式的新`VerticalPageTabViewStyle`。
- **VerticalPageTabViewStyle.TransitionStyle**：标签页之间使用的过渡样式。

## 支持类型

- **DefaultTabViewStyle**：默认选项卡视图样式。
- **SidebarAdaptableTabViewStyle**：适应每个平台的标签栏样式。
- **TabBarOnlyTabViewStyle**：在可能的情况下显示选项卡栏的选项卡视图样式。
- **GroupedTabViewStyle**：一种选项卡视图样式，可显示将选项卡分组在一起的选项卡栏。
- **PageTabViewStyle**：显示分页滚动⟦的`TabViewStyle`。
- **CarouselTabViewStyle**：实现旋转木马交互和外观的样式。

## 符合

- TabViewStyle


---
source: https://developer.apple.com/documentation/swiftui/verticalpagetabviewstyle
crawled: 2025-12-05T22:21:23Z
---

# VerticalPageTabViewStyle

**Structure**

A `TabViewStyle` that displays a vertical `TabView` interaction and appearance.

## Declaration

```swift
struct VerticalPageTabViewStyle
```

## Overview

Use [verticalPage](TabViewStyle/verticalPage.zh-Hans.md) to construct this style.

To apply this style to a tab view, or to a view that contains tab views, use the [tabViewStyle(_:)](View/tabViewStyle.zh-Hans.md) modifier.

## Creating the tab view style

- **init()**
- **init(transitionStyle:)**: Creates a new `VerticalPageTabViewStyle` with a transition style.
- **VerticalPageTabViewStyle.TransitionStyle**: A transition style used between tabs.

## Supporting types

- **DefaultTabViewStyle**: The default tab view style.
- **SidebarAdaptableTabViewStyle**: A tab bar style that adapts to each platform.
- **TabBarOnlyTabViewStyle**: A tab view style that displays a tab bar when possible.
- **GroupedTabViewStyle**: A tab view style that displays a tab bar that groups its tabs together.
- **PageTabViewStyle**: A `TabViewStyle` that displays a paged scrolling `TabView`.
- **CarouselTabViewStyle**: A style that implements the carousel interaction and appearance.

## Conforms To

- TabViewStyle

