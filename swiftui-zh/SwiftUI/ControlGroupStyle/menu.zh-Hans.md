--- 来源：https://developer.apple.com/documentation/SwiftUI/ControlGroupStyle/menu
抓取时间：2025-12-03T06:11:28Z

---

# 菜单

**类型属性**

一种控件组样式，当用户按下控件时，其内容会显示为菜单；当嵌套在更大的菜单中时，则会显示为子菜单。

## 声明

```swift
@MainActor @preconcurrency static var menu: MenuControlGroupStyle { get }
```

## 讨论

要将此样式应用于控件组或包含控件组的视图，请使用 [controlGroupStyle(_:)](../View/controlGroupStyle.zh-Hans.md) 修饰符。

## 获取内置控件组样式

- **automatic**：默认控件组样式。

- **compactMenu**：一种控件组样式，当用户按下控件时，其内容以紧凑菜单的形式呈现；当嵌套在较大的菜单中时，则以子菜单的形式呈现。

- **navigation**：导航控件组样式。

- **palette**：一种控件组样式，其内容以调色板的形式呈现。


---
source: https://developer.apple.com/documentation/SwiftUI/ControlGroupStyle/menu
crawled: 2025-12-03T06:11:28Z
---

# menu

**Type Property**

A control group style that presents its content as a menu when the user presses the control, or as a submenu when nested within a larger menu.

## Declaration

```swift
@MainActor @preconcurrency static var menu: MenuControlGroupStyle { get }
```

## Discussion

To apply this style to a control group, or to a view that contains control groups, use the [controlGroupStyle(_:)](../View/controlGroupStyle.zh-Hans.md) modifier.

## Getting built-in control group styles

- **automatic**: The default control group style.
- **compactMenu**: A control group style that presents its content as a compact menu when the user presses the control, or as a submenu when nested within a larger menu.
- **navigation**: The navigation control group style.
- **palette**: A control group style that presents its content as a palette.

