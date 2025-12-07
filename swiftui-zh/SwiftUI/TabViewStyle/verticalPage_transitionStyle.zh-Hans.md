--- 来源：https://developer.apple.com/documentation/SwiftUI/TabViewStyle/verticalPage(transitionStyle:)

抓取时间：2025-12-01T00:43:33Z

---

# verticalPage(transitionStyle:)

**类型方法**

一个实现垂直页面交互和外观，并执行指定过渡效果的 `TabViewStyle` 方法。

## 声明

```swift
@MainActor @preconcurrency static func verticalPage(transitionStyle: VerticalPageTabViewStyle.TransitionStyle) -> VerticalPageTabViewStyle
```

## 获取内置标签页样式

- **automatic**：默认标签页样式。

- **sidebarAdaptable**：一种能够适应不同平台的标签栏样式。

- **tabBarOnly**：一种尽可能显示标签栏的标签页样式。

- **grouped**：一种标签视图样式，显示一个标签栏，将标签分组在一起。

- **page**：一种 `TabViewStyle`，显示分页滚动 `TabView`。

- **page(indexDisplayMode:)**：一种 `TabViewStyle`，实现分页滚动 `TabView`，并采用索引显示模式。

- **verticalPage**：一种 `TabViewStyle`，显示垂直分页 `TabView` 交互和外观。

- **carousel**：一种实现轮播图交互和外观的样式。


---
source: https://developer.apple.com/documentation/SwiftUI/TabViewStyle/verticalPage(transitionStyle:)
crawled: 2025-12-01T00:43:33Z
---

# verticalPage(transitionStyle:)

**Type Method**

A `TabViewStyle` that implements the vertical page `TabView` interaction and appearance, and performs the specified transition.

## Declaration

```swift
@MainActor @preconcurrency static func verticalPage(transitionStyle: VerticalPageTabViewStyle.TransitionStyle) -> VerticalPageTabViewStyle
```

## Getting built-in tab view styles

- **automatic**: The default tab view style.
- **sidebarAdaptable**: A tab bar style that adapts to each platform.
- **tabBarOnly**: A tab view style that displays a tab bar when possible.
- **grouped**: A tab view style that displays a tab bar that groups its tabs together.
- **page**: A `TabViewStyle` that displays a paged scrolling `TabView`.
- **page(indexDisplayMode:)**: A `TabViewStyle` that implements a paged scrolling `TabView` with an index display mode.
- **verticalPage**: A `TabViewStyle` that displays a vertical page `TabView` interaction and appearance.
- **carousel**: A style that implements the carousel interaction and appearance.

