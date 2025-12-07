---
来源： https://developer.apple.com/documentation/SwiftUI/TabViewStyle
抓取时间： 2025-12-02T17:33:28Z
---

# TabViewStyle

**Protocol**

标签视图的外观和交互规范。

## 声明

```swift
@MainActor @preconcurrency protocol TabViewStyle
```

## 概览

如果符合本协议的类型的基本声明中包含了本协议，那么该类型就继承了本协议的 `@preconcurrency @MainActor` 隔离性：

```swift
struct MyCustomType: Transition {
    // `@preconcurrency @MainActor` isolation by default
}
```

默认情况下与主要角色隔离，但这不是必须的。在扩展声明中声明一致性，就可以不使用主要角色隔离：

```swift
extension MyCustomType: Transition {
    // `nonisolated` by default
}
```

## 获取内置标签视图样式

- **automatic**：默认选项卡视图样式。
- **sidebarAdaptable**：适应每个平台的标签栏样式。
- **tabBarOnly**：在可能的情况下显示选项卡栏的选项卡视图样式。
- **grouped**：一种选项卡视图样式，可显示将选项卡分组在一起的选项卡栏。
- **page**：显示分页滚动⟦的`TabViewStyle`。
- **page(indexDisplayMode:)**：实现分页滚动`TabView` 并具有索引显示模式的`TabViewStyle`。
- **verticalPage**：显示垂直页面`TabView`交互和外观的`TabViewStyle`。
- **verticalPage(transitionStyle:)**：实现垂直页面`TabView`交互和外观并执行指定过渡的`TabViewStyle`。
- **carousel**：实现旋转木马交互和外观的样式。

## 支持类型

- **DefaultTabViewStyle**：默认标签视图样式。
- **SidebarAdaptableTabViewStyle**：适应每个平台的标签栏样式。
- **TabBarOnlyTabViewStyle**：在可能的情况下显示选项卡栏的选项卡视图样式。
- **GroupedTabViewStyle**：一种选项卡视图样式，可显示将选项卡分组在一起的选项卡栏。
- **PageTabViewStyle**：显示分页滚动⟦的`TabViewStyle`。
- **VerticalPageTabViewStyle**：显示垂直`TabViewStyle` 互动和外观的`TabView`。
- **CarouselTabViewStyle**：实现旋转木马交互和外观的样式。

## 导航视图的样式

- **navigationSplitViewStyle(_:)**：为该视图中的导航分割视图设置样式。
- **NavigationSplitViewStyle**：指定视图层次结构中导航分割视图的外观和交互的类型。
- **tabViewStyle(_:)**：为当前环境中的选项卡视图设置样式。

## 符合类型

- 旋转木马标签视图样式
- 默认标签视图样式
- 分组标签视图样式
- 页面标签视图样式
- 侧边栏自适应标签视图样式
- 仅 TabBarTabViewStyle
- 垂直页面标签视图样式


---
source: https://developer.apple.com/documentation/SwiftUI/TabViewStyle
crawled: 2025-12-02T17:33:28Z
---

# TabViewStyle

**Protocol**

A specification for the appearance and interaction of a tab view.

## Declaration

```swift
@MainActor @preconcurrency protocol TabViewStyle
```

## Overview

A type conforming to this protocol inherits `@preconcurrency @MainActor` isolation from the protocol if the conformance is included in the type’s base declaration:

```swift
struct MyCustomType: Transition {
    // `@preconcurrency @MainActor` isolation by default
}
```

Isolation to the main actor is the default, but it’s not required. Declare the conformance in an extension to opt out of main actor isolation:

```swift
extension MyCustomType: Transition {
    // `nonisolated` by default
}
```

## Getting built-in tab view styles

- **automatic**: The default tab view style.
- **sidebarAdaptable**: A tab bar style that adapts to each platform.
- **tabBarOnly**: A tab view style that displays a tab bar when possible.
- **grouped**: A tab view style that displays a tab bar that groups its tabs together.
- **page**: A `TabViewStyle` that displays a paged scrolling `TabView`.
- **page(indexDisplayMode:)**: A `TabViewStyle` that implements a paged scrolling `TabView` with an index display mode.
- **verticalPage**: A `TabViewStyle` that displays a vertical page `TabView` interaction and appearance.
- **verticalPage(transitionStyle:)**: A `TabViewStyle` that implements the vertical page `TabView` interaction and appearance, and performs the specified transition.
- **carousel**: A style that implements the carousel interaction and appearance.

## Supporting types

- **DefaultTabViewStyle**: The default tab view style.
- **SidebarAdaptableTabViewStyle**: A tab bar style that adapts to each platform.
- **TabBarOnlyTabViewStyle**: A tab view style that displays a tab bar when possible.
- **GroupedTabViewStyle**: A tab view style that displays a tab bar that groups its tabs together.
- **PageTabViewStyle**: A `TabViewStyle` that displays a paged scrolling `TabView`.
- **VerticalPageTabViewStyle**: A `TabViewStyle` that displays a vertical `TabView` interaction and appearance.
- **CarouselTabViewStyle**: A style that implements the carousel interaction and appearance.

## Styling navigation views

- **navigationSplitViewStyle(_:)**: Sets the style for navigation split views within this view.
- **NavigationSplitViewStyle**: A type that specifies the appearance and interaction of navigation split views within a view hierarchy.
- **tabViewStyle(_:)**: Sets the style for the tab view within the current environment.

## Conforming Types

- CarouselTabViewStyle
- DefaultTabViewStyle
- GroupedTabViewStyle
- PageTabViewStyle
- SidebarAdaptableTabViewStyle
- TabBarOnlyTabViewStyle
- VerticalPageTabViewStyle

