---
来源： https://developer.apple.com/documentation/SwiftUI/EnvironmentValues/toolbarLabelStyle
抓取时间： 2025-12-02T17:31:25Z
---

# 工具栏标签样式

**实例属性**

应用于工具栏控件的标签样式。

## 声明

```swift
var toolbarLabelStyle: ToolbarLabelStyle? { get }
```

## 讨论

窗口工具栏以外的项目默认使用`nil`。

## 工具栏的样式

- **toolbarBackground(_:for:)**：指定由 SwiftUI 管理的工具栏背景的首选形状样式。
- **toolbarColorScheme(_:for:)**：指定由 SwiftUI 管理的条形图的首选配色方案。
- **toolbarForegroundStyle(_:for:)**：指定由 SwiftUI 管理的条形图的首选颜色方案：指定由 SwiftUI 管理的条形图的首选前景样式。
- **windowToolbarStyle(_:)**：为在此场景中定义的工具栏设置样式。
- **WindowToolbarStyle**：窗口工具栏的外观和行为规范。
- **ToolbarLabelStyle**：工具栏的标签样式。
- **SpacerSizing**：工具栏的标签样式：一种定义间隔符大小的类型。


---
source: https://developer.apple.com/documentation/SwiftUI/EnvironmentValues/toolbarLabelStyle
crawled: 2025-12-02T17:31:25Z
---

# toolbarLabelStyle

**Instance Property**

The label style to apply to controls within a toolbar.

## Declaration

```swift
var toolbarLabelStyle: ToolbarLabelStyle? { get }
```

## Discussion

The default is `nil` for items outside the window toolbar.

## Styling a toolbar

- **toolbarBackground(_:for:)**: Specifies the preferred shape style of the background of a bar managed by SwiftUI.
- **toolbarColorScheme(_:for:)**: Specifies the preferred color scheme of a bar managed by SwiftUI.
- **toolbarForegroundStyle(_:for:)**: Specifies the preferred foreground style of bars managed by SwiftUI.
- **windowToolbarStyle(_:)**: Sets the style for the toolbar defined within this scene.
- **WindowToolbarStyle**: A specification for the appearance and behavior of a window’s toolbar.
- **ToolbarLabelStyle**: The label style of a toolbar.
- **SpacerSizing**: A type which defines how spacers should size themselves.

