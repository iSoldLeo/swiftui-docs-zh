--- 来源：https://developer.apple.com/documentation/SwiftUI/TabViewStyle/grouped

抓取时间：2025-12-02T20:59:28Z

---

# grouped

**类型属性**

一种标签视图样式，用于显示标签栏并将标签分组在一起。

## 声明

```swift
@MainActor @preconcurrency static var grouped: GroupedTabViewStyle { get }
```

## 讨论

要将此样式应用于标签视图或包含标签视图的视图，请使用 [tabViewStyle(_:)](../View/tabViewStyle.zh-Hans.md) 修饰符。

## 获取内置标签视图样式

- **automatic**：默认标签视图样式。

- **sidebarAdaptable**：一种可适应不同平台的标签栏样式。

- **tabBarOnly**：一种尽可能显示标签栏的标签视图样式。

- **page**：一个显示分页滚动效果的 `TabViewStyle` 组件。

- **page(indexDisplayMode:)**：一个实现分页滚动效果的 `TabViewStyle` 组件，并采用索引显示模式。

- **verticalPage**：一个显示垂直分页交互和外观的 `TabViewStyle` 组件。

- **verticalPage(transitionStyle:)**：一个实现垂直分页交互和外观，并执行指定过渡效果的 `TabViewStyle` 组件。

- **carousel**：实现轮播图交互和外观的样式。


---
source: https://developer.apple.com/documentation/SwiftUI/TabViewStyle/grouped
crawled: 2025-12-02T20:59:28Z
---

# grouped

**Type Property**

A tab view style that displays a tab bar that groups its tabs together.

## Declaration

```swift
@MainActor @preconcurrency static var grouped: GroupedTabViewStyle { get }
```

## Discussion

To apply this style to a tab view, or to a view that contains tab views, use the [tabViewStyle(_:)](../View/tabViewStyle.zh-Hans.md) modifier.

## Getting built-in tab view styles

- **automatic**: The default tab view style.
- **sidebarAdaptable**: A tab bar style that adapts to each platform.
- **tabBarOnly**: A tab view style that displays a tab bar when possible.
- **page**: A `TabViewStyle` that displays a paged scrolling `TabView`.
- **page(indexDisplayMode:)**: A `TabViewStyle` that implements a paged scrolling `TabView` with an index display mode.
- **verticalPage**: A `TabViewStyle` that displays a vertical page `TabView` interaction and appearance.
- **verticalPage(transitionStyle:)**: A `TabViewStyle` that implements the vertical page `TabView` interaction and appearance, and performs the specified transition.
- **carousel**: A style that implements the carousel interaction and appearance.

