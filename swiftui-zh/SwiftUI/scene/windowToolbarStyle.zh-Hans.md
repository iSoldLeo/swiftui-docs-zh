--- 来源：https://developer.apple.com/documentation/SwiftUI/Scene/windowToolbarStyle(_:)

抓取时间：2025-12-02T17:21:02Z

---

# windowToolbarStyle(_:)

**实例方法**

设置此场景中定义的工具栏的样式。

## 声明

```swift
nonisolated func windowToolbarStyle<S>(_ style: S) -> some Scene where S : WindowToolbarStyle

```

## 设置工具栏样式

- **toolbarBackground(_:for:)**：指定由 SwiftUI 管理的工具栏背景的首选形状样式。

- **toolbarColorScheme(_:for:)**：指定由 SwiftUI 管理的工具栏的首选配色方案。

- **toolbarForegroundStyle(_:for:)**：指定由 SwiftUI 管理的工具栏的首选前景样式。

- **WindowToolbarStyle**：窗口工具栏外观和行为的规范。

- **toolbarLabelStyle**：应用于工具栏内控件的标签样式。

- **ToolbarLabelStyle**：工具栏的标签样式。

- **SpacerSizing**：定义间隔符如何自动调整大小的类型。


---
source: https://developer.apple.com/documentation/SwiftUI/Scene/windowToolbarStyle(_:)
crawled: 2025-12-02T17:21:02Z
---

# windowToolbarStyle(_:)

**Instance Method**

Sets the style for the toolbar defined within this scene.

## Declaration

```swift
nonisolated func windowToolbarStyle<S>(_ style: S) -> some Scene where S : WindowToolbarStyle

```

## Styling a toolbar

- **toolbarBackground(_:for:)**: Specifies the preferred shape style of the background of a bar managed by SwiftUI.
- **toolbarColorScheme(_:for:)**: Specifies the preferred color scheme of a bar managed by SwiftUI.
- **toolbarForegroundStyle(_:for:)**: Specifies the preferred foreground style of bars managed by SwiftUI.
- **WindowToolbarStyle**: A specification for the appearance and behavior of a window’s toolbar.
- **toolbarLabelStyle**: The label style to apply to controls within a toolbar.
- **ToolbarLabelStyle**: The label style of a toolbar.
- **SpacerSizing**: A type which defines how spacers should size themselves.

