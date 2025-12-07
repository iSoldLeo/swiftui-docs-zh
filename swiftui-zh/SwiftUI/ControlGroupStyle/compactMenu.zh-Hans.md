--- 来源：https://developer.apple.com/documentation/SwiftUI/ControlGroupStyle/compactMenu

抓取时间：2025-12-03T06:11:27Z

---

# compactMenu

**类型属性**

一种控件组样式，当用户按下控件时，其内容会以紧凑菜单的形式呈现；当嵌套在更大的菜单中时，则会以子菜单的形式呈现。

## 声明

```swift
@MainActor @preconcurrency static var compactMenu: CompactMenuControlGroupStyle { get }
```

## 讨论

要将此样式应用于控件组或包含控件组的视图，请使用 [controlGroupStyle(_:)](../View/controlGroupStyle.zh-Hans.md) 修饰符。

## 获取内置控件组样式

- **automatic**：默认控件组样式。

- **menu**：一种控件组样式，当用户按下控件时，其内容会以菜单形式呈现；当嵌套在更大的菜单中时，则会以子菜单形式呈现。

- **navigation**：导航控件组样式。

- **palette**：一种控件组样式，其内容会以调色板形式呈现。


---
source: https://developer.apple.com/documentation/SwiftUI/ControlGroupStyle/compactMenu
crawled: 2025-12-03T06:11:27Z
---

# compactMenu

**Type Property**

A control group style that presents its content as a compact menu when the user presses the control, or as a submenu when nested within a larger menu.

## Declaration

```swift
@MainActor @preconcurrency static var compactMenu: CompactMenuControlGroupStyle { get }
```

## Discussion

To apply this style to a control group, or to a view that contains control groups, use the [controlGroupStyle(_:)](../View/controlGroupStyle.zh-Hans.md) modifier.

## Getting built-in control group styles

- **automatic**: The default control group style.
- **menu**: A control group style that presents its content as a menu when the user presses the control, or as a submenu when nested within a larger menu.
- **navigation**: The navigation control group style.
- **palette**: A control group style that presents its content as a palette.

