--- 来源：https://developer.apple.com/documentation/SwiftUI/TabViewStyle/tabBarOnly
抓取时间：2025-12-02T20:59:27Z

---

# tabBarOnly

**类型属性**

一种标签视图样式，尽可能显示标签栏。

## 声明

```swift
@MainActor @preconcurrency static var tabBarOnly: TabBarOnlyTabViewStyle { get }
```

## 讨论

要将此样式应用于标签视图或包含标签视图的视图，请使用 [tabViewStyle(_:)](../View/tabViewStyle.zh-Hans.md) 修饰符。

## 获取内置标签视图样式

- **automatic**：默认标签视图样式。

- **sidebarAdaptable**：一种适应不同平台的标签栏样式。

- **grouped**：一种标签视图样式，显示一个标签栏，将标签分组在一起。

- **page**：一种 `TabViewStyle`，显示分页滚动 `TabView`。

- **page(indexDisplayMode:)**：一种 `TabViewStyle`，实现分页滚动 `TabView`，并采用索引显示模式。

- **verticalPage**：一种 `TabViewStyle`，显示垂直分页 `TabView` 交互和外观。

- **verticalPage(transitionStyle:)**：实现垂直页面交互和外观的 `TabViewStyle`，并执行指定的过渡效果。

- **carousel**：实现轮播图交互和外观的样式。


---
source: https://developer.apple.com/documentation/SwiftUI/TabViewStyle/tabBarOnly
crawled: 2025-12-02T20:59:27Z
---

# tabBarOnly

**Type Property**

A tab view style that displays a tab bar when possible.

## Declaration

```swift
@MainActor @preconcurrency static var tabBarOnly: TabBarOnlyTabViewStyle { get }
```

## Discussion

To apply this style to a tab view, or to a view that contains tab views, use the [tabViewStyle(_:)](../View/tabViewStyle.zh-Hans.md) modifier.

## Getting built-in tab view styles

- **automatic**: The default tab view style.
- **sidebarAdaptable**: A tab bar style that adapts to each platform.
- **grouped**: A tab view style that displays a tab bar that groups its tabs together.
- **page**: A `TabViewStyle` that displays a paged scrolling `TabView`.
- **page(indexDisplayMode:)**: A `TabViewStyle` that implements a paged scrolling `TabView` with an index display mode.
- **verticalPage**: A `TabViewStyle` that displays a vertical page `TabView` interaction and appearance.
- **verticalPage(transitionStyle:)**: A `TabViewStyle` that implements the vertical page `TabView` interaction and appearance, and performs the specified transition.
- **carousel**: A style that implements the carousel interaction and appearance.

