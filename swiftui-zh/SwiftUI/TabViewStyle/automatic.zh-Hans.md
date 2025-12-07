--- 来源：https://developer.apple.com/documentation/SwiftUI/TabViewStyle/automatic

抓取时间：2025-12-02T20:59:27Z

---

# automatic

**类型属性**

默认标签页视图样式。

## 声明

```swift
@MainActor @preconcurrency static var automatic: DefaultTabViewStyle { get }
```

## 获取内置标签页视图样式

- **sidebarAdaptable**：一种能够适应不同平台的标签栏样式。

- **tabBarOnly**：一种尽可能显示标签栏的标签页视图样式。

- **grouped**：一种将标签分组显示的标签栏样式。

- **page**：一个显示分页滚动效果的 `TabViewStyle` 组件。

- **page(indexDisplayMode:)**：一个实现分页滚动效果的 `TabViewStyle` 组件，并采用索引显示模式。

- **verticalPage**：一个显示垂直分页交互和外观的 `TabViewStyle` 组件。

- **verticalPage(transitionStyle:)**：一个实现垂直分页交互和外观，并执行指定过渡效果的 `TabViewStyle` 组件。

- **carousel**：实现轮播图交互和外观的样式。


---
source: https://developer.apple.com/documentation/SwiftUI/TabViewStyle/automatic
crawled: 2025-12-02T20:59:27Z
---

# automatic

**Type Property**

The default tab view style.

## Declaration

```swift
@MainActor @preconcurrency static var automatic: DefaultTabViewStyle { get }
```

## Getting built-in tab view styles

- **sidebarAdaptable**: A tab bar style that adapts to each platform.
- **tabBarOnly**: A tab view style that displays a tab bar when possible.
- **grouped**: A tab view style that displays a tab bar that groups its tabs together.
- **page**: A `TabViewStyle` that displays a paged scrolling `TabView`.
- **page(indexDisplayMode:)**: A `TabViewStyle` that implements a paged scrolling `TabView` with an index display mode.
- **verticalPage**: A `TabViewStyle` that displays a vertical page `TabView` interaction and appearance.
- **verticalPage(transitionStyle:)**: A `TabViewStyle` that implements the vertical page `TabView` interaction and appearance, and performs the specified transition.
- **carousel**: A style that implements the carousel interaction and appearance.

