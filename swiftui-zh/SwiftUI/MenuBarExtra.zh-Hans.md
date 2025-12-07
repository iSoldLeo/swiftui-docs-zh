--- 来源：https://developer.apple.com/documentation/SwiftUI/MenuBarExtra
抓取时间：2025-12-02T17:20:55Z

---

# MenuBarExtra

**Structure**

一个场景，它会将自身渲染为系统菜单栏中的持久控件。

## 声明

```swift
struct MenuBarExtra<Label, Content> where Label : View, Content : View
```

## 概述

当您希望即使在应用未运行时也能提供常用功能的访问权限时，请使用 `MenuBarExtra`。

```swift
@main
struct AppWithMenuBarExtra: App {
    @AppStorage("showMenuBarExtra") private var showMenuBarExtra = true

    var body: some Scene {
        WindowGroup {
            ContentView()
        }
        MenuBarExtra(
            "App Menu Bar Extra", systemImage: "star",
            isInserted: $showMenuBarExtra)
        {
            StatusMenu()
        }
    }
}
```

或者，您也可以创建一个仅在菜单栏中显示的实用工具应用。

```swift
@main
struct UtilityApp: App {
    var body: some Scene {
        MenuBarExtra("Utility App", systemImage: "hammer") {
            AppMenu()
        }
    }
}
```

如果用户从菜单栏中移除该附加组件，则仅在菜单栏中显示的应用将自动终止。

对于仅显示在菜单栏中的应用，常见的做法是使其图标不显示在 Dock 栏或应用切换器中。要启用此行为，请将应用的 [doc://com.apple.documentation/documentation/BundleResources/Information-Property-List] 文件中的 [doc://com.apple.documentation/documentation/BundleResources/Information-Property-List/LSUIElement] 标志设置为 `true`。

对于更复杂或数据更丰富的菜单栏附加组件，您可以使用 [window](MenuBarExtraStyle/window.zh-Hans.md) 样式，该样式会从菜单栏图标显示一个类似弹出框的窗口，其中包含标准控件。您可以使用提供的内容定义这些控件的布局和内容：

```swift
MenuBarExtra("Utility App", systemImage: "hammer") {
    ScrollView {
        LazyVGrid(...)
    }
}
.menuBarExtraStyle(.window)
```

## 创建菜单栏附加组件

- **init(_:content:)**：创建一个菜单栏附加组件，其中包含一个用于本地化字符串的键，该字符串将用作标签。此附加组件定义了 `App` 的主场景。

- **init(content:label:)**：创建一个菜单栏附加项，该项将显示在系统菜单栏中，并定义 `App` 的主场景。

- **init(_:isInserted:content:)**：创建一个菜单栏附加项，其标签为本地化字符串。当指定的绑定设置为 `true` 时，该项将显示在系统菜单栏中。如果用户从菜单栏中移除该项，则绑定将设置为 `false`。

- **init(isInserted:content:label:)**：创建一个菜单栏附加项。当指定的绑定设置为 `true` 时，该项将显示在系统菜单栏中。如果用户从菜单栏中移除该项，则绑定将设置为 `false`。

## 创建带有图片的菜单栏附加组件

- **init(_:image:content:)**：创建一个带有图片的菜单栏附加组件，该图片将用作项目标签。提供的标题将由辅助功能系统使用。

- **init(_:image:isInserted:content:)**：创建一个带有图片的菜单栏附加组件，该图片将用作项目标签。提供的标题将由辅助功能系统使用。

- **init(_:systemImage:content:)**：创建一个带有系统图片的菜单栏附加组件，该图片将用作项目标签。提供的标题将由辅助功能系统使用。

- **init(_:systemImage:isInserted:content:)**：创建一个带有系统图片的菜单栏附加组件，该图片将用作项目标签。提供的标题将由辅助功能系统使用。

## 创建菜单栏附加组件

- **menuBarExtraStyle(_:)**：设置此场景创建的菜单栏附加组件的样式。

- **MenuBarExtraStyle**：菜单栏附加场景的外观和行为规范。

## 符合以下规范

- 场景


---
source: https://developer.apple.com/documentation/SwiftUI/MenuBarExtra
crawled: 2025-12-02T17:20:55Z
---

# MenuBarExtra

**Structure**

A scene that renders itself as a persistent control in the system menu bar.

## Declaration

```swift
struct MenuBarExtra<Label, Content> where Label : View, Content : View
```

## Overview

Use a `MenuBarExtra` when you want to provide access to commonly used functionality, even when your app is not active.

```swift
@main
struct AppWithMenuBarExtra: App {
    @AppStorage("showMenuBarExtra") private var showMenuBarExtra = true

    var body: some Scene {
        WindowGroup {
            ContentView()
        }
        MenuBarExtra(
            "App Menu Bar Extra", systemImage: "star",
            isInserted: $showMenuBarExtra)
        {
            StatusMenu()
        }
    }
}
```

Or alternatively, to create a utility app that only shows in the menu bar.

```swift
@main
struct UtilityApp: App {
    var body: some Scene {
        MenuBarExtra("Utility App", systemImage: "hammer") {
            AppMenu()
        }
    }
}
```

An app that only shows in the menu bar will be automatically terminated if the user removes the extra from the menu bar.

For apps that only show in the menu bar, a common behavior is for the app to not display its icon in either the Dock or the application switcher. To enable this behavior, set the [doc://com.apple.documentation/documentation/BundleResources/Information-Property-List/LSUIElement] flag in your app’s [doc://com.apple.documentation/documentation/BundleResources/Information-Property-List] file to `true`.

For more complex or data rich menu bar extras, you can use the [window](MenuBarExtraStyle/window.zh-Hans.md) style, which displays a popover-like window from the menu bar icon that contains standard controls. You define the layout and contents of those controls with the content that you provide:

```swift
MenuBarExtra("Utility App", systemImage: "hammer") {
    ScrollView {
        LazyVGrid(...)
    }
}
.menuBarExtraStyle(.window)
```

## Creating a menu bar extra

- **init(_:content:)**: Creates a menu bar extra with a key for a localized string to use as the label. The extra defines the primary scene of an `App`.
- **init(content:label:)**: Creates a menu bar extra that will be displayed in the system menu bar, and defines the primary scene of an `App`.
- **init(_:isInserted:content:)**: Creates a menu bar extra with a key for a localized string to use as the label. The item will be displayed in the system menu bar when the specified binding is set to `true`. If the user removes the item from the menu bar, the binding will be set to `false`.
- **init(isInserted:content:label:)**: Creates a menu bar extra. The item will be displayed in the system menu bar when the specified binding is set to `true`. If the user removes the item from the menu bar, the binding will be set to `false`.

## Creating a menu bar extra with an image

- **init(_:image:content:)**: Creates a menu bar extra with an image to use as the items label. The provided title will be used by the accessibility system.
- **init(_:image:isInserted:content:)**: Creates a menu bar extra with an image to use as the items label. The provided title will be used by the accessibility system.
- **init(_:systemImage:content:)**: Creates a menu bar extra with a system image to use as the items label. The provided title will be used by the accessibility system.
- **init(_:systemImage:isInserted:content:)**: Creates a menu bar extra with a system image to use as the items label. The provided title will be used by the accessibility system.

## Creating a menu bar extra

- **menuBarExtraStyle(_:)**: Sets the style for menu bar extra created by this scene.
- **MenuBarExtraStyle**: A specification for the appearance and behavior of a menu bar extra scene.

## Conforms To

- Scene

