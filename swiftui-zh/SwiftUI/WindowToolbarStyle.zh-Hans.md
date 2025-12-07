---
来源： https://developer.apple.com/documentation/SwiftUI/WindowToolbarStyle
抓取时间： 2025-12-02T17:21:04Z
---

# WindowToolbarStyle

**Protocol**

窗口工具栏外观和行为的规范。

## 声明

```swift
protocol WindowToolbarStyle
```

## 获取内置窗口工具栏样式

- **automatic**：自动窗口工具栏样式。
- **expanded**：在工具栏上方显示标题栏区域的窗口工具栏样式。
- **unified**：一种窗口工具栏样式，它以内联方式显示工具栏和标题栏。
- **unified(showsTitle:)**：窗口工具栏样式，以内联方式显示工具栏和标题栏。
- **unifiedCompact**：与[unified](WindowToolbarStyle/unified.zh-Hans.md)相似的窗口工具栏样式，但垂直尺寸更紧凑。
- **unifiedCompact(showsTitle:)**：窗口工具栏样式类似于 [unified](WindowToolbarStyle/unified.zh-Hans.md)，但垂直尺寸更紧凑。

## 支持类型

- **DefaultWindowToolbarStyle**：默认窗口工具栏样式。
- **ExpandedWindowToolbarStyle**：在工具栏上方显示标题栏区域的窗口工具栏样式。
- **UnifiedWindowToolbarStyle**：一种窗口工具栏样式，它以内联方式显示工具栏和标题栏。
- **UnifiedCompactWindowToolbarStyle**：与 [unified](WindowToolbarStyle/unified.zh-Hans.md) 相似的窗口工具栏样式，但垂直尺寸更紧凑。

## 工具栏样式

- **toolbarBackground(_:for:)**：指定由 SwiftUI 管理的工具栏背景的首选形状样式。
- **toolbarColorScheme(_:for:)**：指定由 SwiftUI 管理的条形图的首选配色方案。
- **toolbarForegroundStyle(_:for:)**：指定由 SwiftUI 管理的条形图的首选前景样式。
- **windowToolbarStyle(_:)**：为在此场景中定义的工具栏设置样式。
- **toolbarLabelStyle**：应用于工具栏内控件的标签样式。
- **ToolbarLabelStyle**：工具栏的标签样式。
- **SpacerSizing**：工具栏的标签样式：一种定义间隔符大小的类型。

## 符合类型

- 默认窗口工具栏样式（DefaultWindowToolbarStyle
- 扩展窗口工具栏样式
- 统一紧凑窗口工具栏样式
- 统一窗口工具栏样式


---
source: https://developer.apple.com/documentation/SwiftUI/WindowToolbarStyle
crawled: 2025-12-02T17:21:04Z
---

# WindowToolbarStyle

**Protocol**

A specification for the appearance and behavior of a window’s toolbar.

## Declaration

```swift
protocol WindowToolbarStyle
```

## Getting built-in window toolbar styles

- **automatic**: The automatic window toolbar style.
- **expanded**: A window toolbar style which displays its title bar area above the toolbar.
- **unified**: A window toolbar style which displays its toolbar and title bar inline.
- **unified(showsTitle:)**: A window toolbar style which displays its toolbar and title bar inline.
- **unifiedCompact**: A window toolbar style similar to [unified](WindowToolbarStyle/unified.zh-Hans.md), but with a more compact vertical sizing.
- **unifiedCompact(showsTitle:)**: A window toolbar style similar to [unified](WindowToolbarStyle/unified.zh-Hans.md), but with a more compact vertical sizing.

## Supporting types

- **DefaultWindowToolbarStyle**: The default window toolbar style.
- **ExpandedWindowToolbarStyle**: A window toolbar style which displays its title bar area above the toolbar.
- **UnifiedWindowToolbarStyle**: A window toolbar style which displays its toolbar and title bar inline.
- **UnifiedCompactWindowToolbarStyle**: A window toolbar style similar to [unified](WindowToolbarStyle/unified.zh-Hans.md), but with a more compact vertical sizing.

## Styling a toolbar

- **toolbarBackground(_:for:)**: Specifies the preferred shape style of the background of a bar managed by SwiftUI.
- **toolbarColorScheme(_:for:)**: Specifies the preferred color scheme of a bar managed by SwiftUI.
- **toolbarForegroundStyle(_:for:)**: Specifies the preferred foreground style of bars managed by SwiftUI.
- **windowToolbarStyle(_:)**: Sets the style for the toolbar defined within this scene.
- **toolbarLabelStyle**: The label style to apply to controls within a toolbar.
- **ToolbarLabelStyle**: The label style of a toolbar.
- **SpacerSizing**: A type which defines how spacers should size themselves.

## Conforming Types

- DefaultWindowToolbarStyle
- ExpandedWindowToolbarStyle
- UnifiedCompactWindowToolbarStyle
- UnifiedWindowToolbarStyle

