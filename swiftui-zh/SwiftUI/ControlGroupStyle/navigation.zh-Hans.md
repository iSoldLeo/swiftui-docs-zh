--- 来源：https://developer.apple.com/documentation/SwiftUI/ControlGroupStyle/navigation
抓取时间：2025-12-03T06:11:29Z

---

# navigation

**类型属性**

导航控件组样式。

## 声明

```swift
@MainActor @preconcurrency static var navigation: NavigationControlGroupStyle { get }
```

## 讨论

使用此样式对与导航相关的控件进行分组，例如后退/前进按钮或时间轴导航控件。

导航控件组样式可能因平台而异。在 iOS 上，它渲染为单独的无边框按钮；而在 macOS 上，它显示为分离的、短暂的分段控件。

要将此样式应用于控件组或包含控件组的视图，请使用 [controlGroupStyle(_:)](../View/controlGroupStyle.zh-Hans.md) 修饰符。

## 获取内置控件组样式

- **automatic**：默认控件组样式。

- **compactMenu**：一种控件组样式，当用户按下控件时，其内容以紧凑菜单的形式呈现；当嵌套在更大的菜单中时，则以子菜单的形式呈现。

- **menu**：一种控件组样式，当用户按下控件时，其内容以菜单的形式呈现；当嵌套在更大的菜单中时，则以子菜单的形式呈现。

- **palette**：一种控件组样式，其内容以调色板的形式呈现。


---
source: https://developer.apple.com/documentation/SwiftUI/ControlGroupStyle/navigation
crawled: 2025-12-03T06:11:29Z
---

# navigation

**Type Property**

The navigation control group style.

## Declaration

```swift
@MainActor @preconcurrency static var navigation: NavigationControlGroupStyle { get }
```

## Discussion

Use this style to group controls related to navigation, such as back/forward buttons or timeline navigation controls.

The navigation control group style can vary by platform. On iOS, it renders as individual borderless buttons, while on macOS, it displays as a separated momentary segmented control.

To apply this style to a control group or to a view that contains a control group, use the [controlGroupStyle(_:)](../View/controlGroupStyle.zh-Hans.md) modifier.

## Getting built-in control group styles

- **automatic**: The default control group style.
- **compactMenu**: A control group style that presents its content as a compact menu when the user presses the control, or as a submenu when nested within a larger menu.
- **menu**: A control group style that presents its content as a menu when the user presses the control, or as a submenu when nested within a larger menu.
- **palette**: A control group style that presents its content as a palette.

