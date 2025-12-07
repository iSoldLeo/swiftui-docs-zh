--- 来源：https://developer.apple.com/documentation/SwiftUI/View/toolbarBackground(_:for:)

抓取时间：2025-11-30T21:16:28Z

---

# toolbarBackground(_:for:)

**实例方法**

指定 SwiftUI 管理的工具栏背景的首选形状样式。

## 声明

```swift
nonisolated func toolbarBackground<S>(_ style: S, for bars: ToolbarPlacement...) -> some View where S : ShapeStyle

```

## 参数

- **style**：要用作工具栏背景的样式。

- **bars**：要应用此样式的工具栏，如果为空则为 [automatic](../ToolbarPlacement/automatic.zh-Hans.md)。

## 说明

首选样式会应用到渲染工具栏的最近的容器。在 iOS 中，这可能是 [NavigationView](../NavigationView.zh-Hans.md) 或 [TabView](../TabView.zh-Hans.md)，在 macOS 中，这可能是 [WindowGroup](../WindowGroup.zh-Hans.md) 的根视图。此示例展示了一个以蓝色背景和深色配色方案渲染导航栏的视图。

```swift
NavigationView {
    ContentView()
        .toolbarBackground(.white)
        .toolbarColorScheme(.dark)
}
```

您可以提供多个 [ToolbarPlacement](../ToolbarPlacement.zh-Hans.md) 实例来同时自定义多个导航栏。

```swift
TabView {
    NavigationView {
        ContentView()
            .toolbarBackground(
                .blue, for: .navigationBar, .tabBar)
            .toolbarColorScheme(
                .dark, for: .navigationBar, .tabBar)
    }
}
```

在 [TabView](../TabView.zh-Hans.md) 中使用时，指定样式将在标签页处于活动状态时优先使用。您可以使用 [Group](../Group.zh-Hans.md) 为每个标签页指定相同的首选背景。

```swift
TabView {
    Group {
        MainView()
        SettingsView()
    }
    .toolbarBackground(.blue, for: .tabBar)
}
```

根据指定的导航栏，可能无法完全实现请求的样式。

## 设置工具栏样式

- **toolbarColorScheme(_:for:)**：指定由 SwiftUI 管理的工具栏的首选配色方案。

- **toolbarForegroundStyle(_:for:)**：指定由 SwiftUI 管理的工具栏的首选前景样式。

- **windowToolbarStyle(_:)**：设置此场景中定义的工具栏的样式。

- **WindowToolbarStyle**：窗口工具栏的外观和行为规范。

- **toolbarLabelStyle**：要应用于工具栏内控件的标签样式。

- **ToolbarLabelStyle**：工具栏的标签样式。

- **SpacerSizing**：定义间隔符如何自动调整大小的类型。


---
source: https://developer.apple.com/documentation/SwiftUI/View/toolbarBackground(_:for:)
crawled: 2025-11-30T21:16:28Z
---

# toolbarBackground(_:for:)

**Instance Method**

Specifies the preferred shape style of the background of a bar managed by SwiftUI.

## Declaration

```swift
nonisolated func toolbarBackground<S>(_ style: S, for bars: ToolbarPlacement...) -> some View where S : ShapeStyle

```

## Parameters

- **style**: The style to display as the background of the bar.
- **bars**: The bars to use the style for or [automatic](../ToolbarPlacement/automatic.zh-Hans.md) if empty.

## Discussion

The preferred style flows up to the nearest container that renders a bar. This could be a [NavigationView](../NavigationView.zh-Hans.md) or [TabView](../TabView.zh-Hans.md) in iOS, or the root view of a [WindowGroup](../WindowGroup.zh-Hans.md) in macOS. This example shows a view that renders the navigation bar with a blue background and dark color scheme.

```swift
NavigationView {
    ContentView()
        .toolbarBackground(.white)
        .toolbarColorScheme(.dark)
}
```

You can provide multiple [ToolbarPlacement](../ToolbarPlacement.zh-Hans.md) instances to customize multiple bars at once.

```swift
TabView {
    NavigationView {
        ContentView()
            .toolbarBackground(
                .blue, for: .navigationBar, .tabBar)
            .toolbarColorScheme(
                .dark, for: .navigationBar, .tabBar)
    }
}
```

When used within a [TabView](../TabView.zh-Hans.md), the specified style will be preferred while the tab is currently active. You can use a [Group](../Group.zh-Hans.md) to specify the same preferred background for every tab.

```swift
TabView {
    Group {
        MainView()
        SettingsView()
    }
    .toolbarBackground(.blue, for: .tabBar)
}
```

Depending on the specified bars, the requested style may not be able to be fullfilled.

## Styling a toolbar

- **toolbarColorScheme(_:for:)**: Specifies the preferred color scheme of a bar managed by SwiftUI.
- **toolbarForegroundStyle(_:for:)**: Specifies the preferred foreground style of bars managed by SwiftUI.
- **windowToolbarStyle(_:)**: Sets the style for the toolbar defined within this scene.
- **WindowToolbarStyle**: A specification for the appearance and behavior of a window’s toolbar.
- **toolbarLabelStyle**: The label style to apply to controls within a toolbar.
- **ToolbarLabelStyle**: The label style of a toolbar.
- **SpacerSizing**: A type which defines how spacers should size themselves.

