--- 来源：https://developer.apple.com/documentation/SwiftUI/View/toolbarColorScheme(_:for:)

抓取时间：2025-12-02T17:31:24Z

---

# toolbarColorScheme(_:for:)

**实例方法**

指定由 SwiftUI 管理的工具栏的首选配色方案。

## 声明

```swift
nonisolated func toolbarColorScheme(_ colorScheme: ColorScheme?, for bars: ToolbarPlacement...) -> some View

```

## 参数

- **colorScheme**：工具栏背景的首选配色方案。

- **bars**：要更新配色方案的工具栏，如果为空则为 [automatic](../ToolbarPlacement/automatic.zh-Hans.md)。

## 说明

首选配色方案会应用到渲染工具栏的最近的容器。在 iOS 系统中，这可能是 [NavigationView](../NavigationView.zh-Hans.md) 或 [TabView](../TabView.zh-Hans.md)，在 macOS 系统中，这可能是 [WindowGroup](../WindowGroup.zh-Hans.md) 的根视图。传入 nil 值可匹配当前系统的配色方案。

以下示例展示了一个使用蓝色背景和深色配色方案渲染导航栏的视图：

```swift
TabView {
    NavigationView {
        ContentView()
            .toolbarBackground(.blue)
            .toolbarColorScheme(.dark)
    }
    // other tabs...
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

请注意，提供的配色方案仅在请求的导航栏显示背景时生效。当背景变为可见时，导航栏会从应用程序的配色方案过渡到请求的配色方案。您可以通过指定导航栏的背景始终可见来确保始终应用该配色方案。

```swift
NavigationView {
    ContentView()
        .toolbarBackground(.visible)
        .toolbarColorScheme(.dark)
}
```

根据指定的工具栏，可能无法完全实现请求的配色方案。

## 工具栏样式

- **toolbarBackground(_:for:)**：指定由 SwiftUI 管理的工具栏背景的首选形状样式。

- **toolbarForegroundStyle(_:for:)**：指定由 SwiftUI 管理的工具栏的首选前景样式。

- **windowToolbarStyle(_:)**：设置此场景中定义的工具栏的样式。

- **WindowToolbarStyle**：窗口工具栏的外观和行为规范。

- **toolbarLabelStyle**：要应用于工具栏内控件的标签样式。

- **ToolbarLabelStyle**：工具栏的标签样式。

- **SpacerSizing**：定义间隔符如何自动调整大小的类型。


---
source: https://developer.apple.com/documentation/SwiftUI/View/toolbarColorScheme(_:for:)
crawled: 2025-12-02T17:31:24Z
---

# toolbarColorScheme(_:for:)

**Instance Method**

Specifies the preferred color scheme of a bar managed by SwiftUI.

## Declaration

```swift
nonisolated func toolbarColorScheme(_ colorScheme: ColorScheme?, for bars: ToolbarPlacement...) -> some View

```

## Parameters

- **colorScheme**: The preferred color scheme of the background of the bar.
- **bars**: The bars to update the color scheme of or [automatic](../ToolbarPlacement/automatic.zh-Hans.md) if empty.

## Discussion

The preferred color scheme flows up to the nearest container that renders a bar. This could be a [NavigationView](../NavigationView.zh-Hans.md) or [TabView](../TabView.zh-Hans.md) in iOS, or the root view of a [WindowGroup](../WindowGroup.zh-Hans.md) in macOS. Pass in a value of nil to match the current system’s color scheme.

This examples shows a view that renders the navigation bar with a blue background and dark color scheme:

```swift
TabView {
    NavigationView {
        ContentView()
            .toolbarBackground(.blue)
            .toolbarColorScheme(.dark)
    }
    // other tabs...
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

Note that the provided color scheme is only respected while a background is visible in the requested bar. As the background becomes visible, the bar transitions from the color scheme of the app to the requested color scheme. You can ensure that the color scheme is always respected by specifying that the background of the bar always be visible.

```swift
NavigationView {
    ContentView()
        .toolbarBackground(.visible)
        .toolbarColorScheme(.dark)
}
```

Depending on the specified bars, the requested color scheme may not be able to be fullfilled.

## Styling a toolbar

- **toolbarBackground(_:for:)**: Specifies the preferred shape style of the background of a bar managed by SwiftUI.
- **toolbarForegroundStyle(_:for:)**: Specifies the preferred foreground style of bars managed by SwiftUI.
- **windowToolbarStyle(_:)**: Sets the style for the toolbar defined within this scene.
- **WindowToolbarStyle**: A specification for the appearance and behavior of a window’s toolbar.
- **toolbarLabelStyle**: The label style to apply to controls within a toolbar.
- **ToolbarLabelStyle**: The label style of a toolbar.
- **SpacerSizing**: A type which defines how spacers should size themselves.

