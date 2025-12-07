--- 来源：https://developer.apple.com/documentation/SwiftUI/ControlGroupStyle/automatic

抓取时间：2025-12-03T06:11:27Z

---

# automatic

**类型属性**

默认控件组样式。

## 声明

```swift
@MainActor @preconcurrency static var automatic: AutomaticControlGroupStyle { get }
```

## 讨论

默认控件组样式可能因平台而异。默认情况下，所有平台都使用适合其渲染环境的瞬时分段控件样式。

您可以覆盖控件组的样式。要将默认样式应用于控件组或包含控件组的视图，请使用 [controlGroupStyle(_:)](../View/controlGroupStyle.zh-Hans.md) 修饰符。

## 获取内置控件组样式

- **compactMenu**：一种控件组样式，当用户按下控件时，其内容以紧凑菜单的形式呈现；当嵌套在更大的菜单中时，则以子菜单的形式呈现。

- **menu**：一种控件组样式，当用户按下控件时，其内容以菜单的形式呈现；当嵌套在更大的菜单中时，则以子菜单的形式呈现。

- **navigation**：导航控件组样式。

- **palette**：一种控件组样式，其内容以调色板的形式呈现。


---
source: https://developer.apple.com/documentation/SwiftUI/ControlGroupStyle/automatic
crawled: 2025-12-03T06:11:27Z
---

# automatic

**Type Property**

The default control group style.

## Declaration

```swift
@MainActor @preconcurrency static var automatic: AutomaticControlGroupStyle { get }
```

## Discussion

The default control group style can vary by platform. By default, both platforms use a momentary segmented control style that’s appropriate for the environment in which it is rendered.

You can override a control group’s style. To apply the default style to a control group or to a view that contains a control group, use the [controlGroupStyle(_:)](../View/controlGroupStyle.zh-Hans.md) modifier.

## Getting built-in control group styles

- **compactMenu**: A control group style that presents its content as a compact menu when the user presses the control, or as a submenu when nested within a larger menu.
- **menu**: A control group style that presents its content as a menu when the user presses the control, or as a submenu when nested within a larger menu.
- **navigation**: The navigation control group style.
- **palette**: A control group style that presents its content as a palette.

