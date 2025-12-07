--- 来源：https://developer.apple.com/documentation/SwiftUI/TabViewStyle/verticalPage
抓取时间：2025-12-02T20:59:30Z

---

# verticalPage

**类型属性**

一个用于显示垂直页面交互和外观的 `TabViewStyle` 属性。

## 声明

```swift
@MainActor @preconcurrency static var verticalPage: VerticalPageTabViewStyle { get }
```

## 讨论

要将此样式应用于选项卡视图或包含选项卡视图的视图，请使用 [tabViewStyle(_:)](../View/tabViewStyle.zh-Hans.md) 修饰符。

## 获取内置选项卡视图样式

- **automatic**：默认选项卡视图样式。

- **sidebarAdaptable**：一种可适应不同平台的选项卡栏样式。

- **tabBarOnly**：一种尽可能显示标签栏的标签视图样式。

- **grouped**：一种显示标签栏并将标签分组在一起的标签视图样式。

- **page**：一种显示分页滚动效果的 `TabViewStyle` 样式。

- **page(indexDisplayMode:)**：一种实现分页滚动效果的 `TabViewStyle` 样式，并采用索引显示模式。

- **verticalPage(transitionStyle:)**：一种实现垂直分页交互和外观，并执行指定过渡效果的 `TabViewStyle` 样式。

- **carousel**：实现轮播图交互和外观的样式。


---
source: https://developer.apple.com/documentation/SwiftUI/TabViewStyle/verticalPage
crawled: 2025-12-02T20:59:30Z
---

# verticalPage

**Type Property**

A `TabViewStyle` that displays a vertical page `TabView` interaction and appearance.

## Declaration

```swift
@MainActor @preconcurrency static var verticalPage: VerticalPageTabViewStyle { get }
```

## Discussion

To apply this style to a tab view, or to a view that contains tab views, use the [tabViewStyle(_:)](../View/tabViewStyle.zh-Hans.md) modifier.

## Getting built-in tab view styles

- **automatic**: The default tab view style.
- **sidebarAdaptable**: A tab bar style that adapts to each platform.
- **tabBarOnly**: A tab view style that displays a tab bar when possible.
- **grouped**: A tab view style that displays a tab bar that groups its tabs together.
- **page**: A `TabViewStyle` that displays a paged scrolling `TabView`.
- **page(indexDisplayMode:)**: A `TabViewStyle` that implements a paged scrolling `TabView` with an index display mode.
- **verticalPage(transitionStyle:)**: A `TabViewStyle` that implements the vertical page `TabView` interaction and appearance, and performs the specified transition.
- **carousel**: A style that implements the carousel interaction and appearance.

