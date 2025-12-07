--- 来源：https://developer.apple.com/documentation/SwiftUI/TabViewStyle/sidebarAdaptable
抓取时间：2025-12-02T16:23:29Z

---

# sidebarAdaptable

**类型属性**

一种能够适应不同平台的标签栏样式。

## 声明

```swift
@MainActor @preconcurrency static var sidebarAdaptable: SidebarAdaptableTabViewStyle { get }
```

## 讨论

使用 sidebarAdaptable 样式的标签视图在不同平台上的外观有所不同：

- iPadOS 显示顶部标签栏，该标签栏可以适应为侧边栏。

- iOS 显示底部标签栏。

- macOS 和 tvOS 始终显示侧边栏。

- VisionOS 显示装饰效果，并在 [TabSection](../TabSection.zh-Hans.md) 内显示辅助标签的侧边栏。

要将此样式应用于选项卡视图或包含选项卡视图的视图，请使用 [tabViewStyle(_:)](../View/tabViewStyle.zh-Hans.md) 修饰符。

## 获取内置选项卡视图样式

- **automatic**：默认选项卡视图样式。

- **tabBarOnly**：尽可能显示选项卡栏的选项卡视图样式。

- **grouped**：显示选项卡栏并将选项卡分组在一起的选项卡视图样式。

- **page**：显示分页滚动 `TabView` 的 `TabViewStyle`。

- **page(indexDisplayMode:)**：实现分页滚动 `TabView` 并启用索引显示模式的 `TabViewStyle`。

- **verticalPage**：一个用于显示垂直页面交互和外观的 `TabViewStyle`。

- **verticalPage(transitionStyle:)**：一个实现垂直页面交互和外观，并执行指定过渡效果的 `TabViewStyle`。

- **carousel**：一个实现轮播图交互和外观的样式。


---
source: https://developer.apple.com/documentation/SwiftUI/TabViewStyle/sidebarAdaptable
crawled: 2025-12-02T16:23:29Z
---

# sidebarAdaptable

**Type Property**

A tab bar style that adapts to each platform.

## Declaration

```swift
@MainActor @preconcurrency static var sidebarAdaptable: SidebarAdaptableTabViewStyle { get }
```

## Discussion

Tab views using the sidebar adaptable style have an appearance that varies depending on the platform:

- iPadOS displays a top tab bar that can adapt into a sidebar.
- iOS displays a bottom tab bar.
- macOS and tvOS always show a sidebar.
- visionOS shows an ornament and also shows a sidebar for secondary tabs within a [TabSection](../TabSection.zh-Hans.md).

To apply this style to a tab view, or to a view that contains tab views, use the [tabViewStyle(_:)](../View/tabViewStyle.zh-Hans.md) modifier.

## Getting built-in tab view styles

- **automatic**: The default tab view style.
- **tabBarOnly**: A tab view style that displays a tab bar when possible.
- **grouped**: A tab view style that displays a tab bar that groups its tabs together.
- **page**: A `TabViewStyle` that displays a paged scrolling `TabView`.
- **page(indexDisplayMode:)**: A `TabViewStyle` that implements a paged scrolling `TabView` with an index display mode.
- **verticalPage**: A `TabViewStyle` that displays a vertical page `TabView` interaction and appearance.
- **verticalPage(transitionStyle:)**: A `TabViewStyle` that implements the vertical page `TabView` interaction and appearance, and performs the specified transition.
- **carousel**: A style that implements the carousel interaction and appearance.

