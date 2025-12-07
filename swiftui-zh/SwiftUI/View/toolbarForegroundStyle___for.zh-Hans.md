--- 来源：https://developer.apple.com/documentation/SwiftUI/View/toolbarForegroundStyle(_:for:)

抓取时间：2025-11-30T21:16:30Z

---

# toolbarForegroundStyle(_:for:)

**实例方法**

指定 SwiftUI 管理的工具栏的首选前景样式。

## 声明

```swift
nonisolated func toolbarForegroundStyle<S>(_ style: S, for bars: ToolbarPlacement...) -> some View where S : ShapeStyle

```

## 说明

此示例展示了一个使用蓝色前景渲染导航栏的视图。

```swift
NavigationStack {
    ContentView()
        .navigationTitle("Blue")
        .toolbarForegroundStyle(
            .blue, for: .navigationBar)
}
```

## 设置工具栏样式

- **toolbarBackground(_:for:)**：指定 SwiftUI 管理的工具栏背景的首选形状样式。

- **toolbarColorScheme(_:for:)**：指定 SwiftUI 管理的工具栏的首选配色方案。

- **windowToolbarStyle(_:)**：设置此场景中定义的工具栏的样式。

- **WindowToolbarStyle**：窗口工具栏的外观和行为规范。

- **toolbarLabelStyle**：应用于工具栏内控件的标签样式。

- **ToolbarLabelStyle**：工具栏的标签样式。

- **SpacerSizing**：定义间隔符如何自动调整大小的类型。


---
source: https://developer.apple.com/documentation/SwiftUI/View/toolbarForegroundStyle(_:for:)
crawled: 2025-11-30T21:16:30Z
---

# toolbarForegroundStyle(_:for:)

**Instance Method**

Specifies the preferred foreground style of bars managed by SwiftUI.

## Declaration

```swift
nonisolated func toolbarForegroundStyle<S>(_ style: S, for bars: ToolbarPlacement...) -> some View where S : ShapeStyle

```

## Discussion

This examples shows a view that renders the navigation bar with a blue foreground color.

```swift
NavigationStack {
    ContentView()
        .navigationTitle("Blue")
        .toolbarForegroundStyle(
            .blue, for: .navigationBar)
}
```

## Styling a toolbar

- **toolbarBackground(_:for:)**: Specifies the preferred shape style of the background of a bar managed by SwiftUI.
- **toolbarColorScheme(_:for:)**: Specifies the preferred color scheme of a bar managed by SwiftUI.
- **windowToolbarStyle(_:)**: Sets the style for the toolbar defined within this scene.
- **WindowToolbarStyle**: A specification for the appearance and behavior of a window’s toolbar.
- **toolbarLabelStyle**: The label style to apply to controls within a toolbar.
- **ToolbarLabelStyle**: The label style of a toolbar.
- **SpacerSizing**: A type which defines how spacers should size themselves.

