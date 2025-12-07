--- 来源：https://developer.apple.com/documentation/SwiftUI/TabViewStyle/page(indexDisplayMode:)

抓取时间：2025-12-01T00:43:32Z

---

# page(indexDisplayMode:)

**类型方法**

一个实现分页滚动（索引显示模式）的 `TabViewStyle` 方法。

## 声明

```swift
@MainActor @preconcurrency static func page(indexDisplayMode: PageTabViewStyle.IndexDisplayMode) -> PageTabViewStyle
```

## 讨论

要将此样式应用于标签视图或包含标签视图的视图，请使用 [tabViewStyle(_:)](../View/tabViewStyle.zh-Hans.md) 修饰符。

## 获取内置标签视图样式

- **automatic**：默认标签视图样式。

- **sidebarAdaptable**：一种可适应各个平台的标签栏样式。

- **tabBarOnly**：一种尽可能显示标签栏的标签视图样式。

- **grouped**：一种将标签分组显示的标签栏的标签视图样式。

- **page**：一种显示分页滚动效果的 `TabViewStyle` 样式。

- **verticalPage**：一种显示垂直页面交互和外观的 `TabViewStyle` 样式。

- **verticalPage(transitionStyle:)**：实现垂直页面交互和外观的 `TabViewStyle`，并执行指定的过渡效果。

- **carousel**：实现轮播图交互和外观的样式。


---
source: https://developer.apple.com/documentation/SwiftUI/TabViewStyle/page(indexDisplayMode:)
crawled: 2025-12-01T00:43:32Z
---

# page(indexDisplayMode:)

**Type Method**

A `TabViewStyle` that implements a paged scrolling `TabView` with an index display mode.

## Declaration

```swift
@MainActor @preconcurrency static func page(indexDisplayMode: PageTabViewStyle.IndexDisplayMode) -> PageTabViewStyle
```

## Discussion

To apply this style to a tab view, or to a view that contains tab views, use the [tabViewStyle(_:)](../View/tabViewStyle.zh-Hans.md) modifier.

## Getting built-in tab view styles

- **automatic**: The default tab view style.
- **sidebarAdaptable**: A tab bar style that adapts to each platform.
- **tabBarOnly**: A tab view style that displays a tab bar when possible.
- **grouped**: A tab view style that displays a tab bar that groups its tabs together.
- **page**: A `TabViewStyle` that displays a paged scrolling `TabView`.
- **verticalPage**: A `TabViewStyle` that displays a vertical page `TabView` interaction and appearance.
- **verticalPage(transitionStyle:)**: A `TabViewStyle` that implements the vertical page `TabView` interaction and appearance, and performs the specified transition.
- **carousel**: A style that implements the carousel interaction and appearance.

