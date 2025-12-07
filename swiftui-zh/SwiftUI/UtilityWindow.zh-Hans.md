--- 来源：https://developer.apple.com/documentation/SwiftUI/UtilityWindow

抓取时间：2025-12-02T17:21:00Z

---

# UtilityWindow

**Structure**

一个特殊的窗口场景，为应用程序的主场景内容提供辅助功能。

## 声明

```swift
struct UtilityWindow<Content> where Content : View
```

## 概述

实用工具窗口通常用于显示与应用程序主内容相关的控件、设置或信息，有时也称为工具面板或检查器窗口。由于其特殊用途，它们与其他窗口相比具有特殊行为：

- 它们接收来自应用程序中当前聚焦的主场景的 `FocusedValues` 信息，类似于主菜单中的命令，可用于在用户聚焦于不同场景时显示有关活动内容的信息。

- 它们的默认窗口级别为 `.floating`，因此在主场景之间切换焦点时，它们始终可见。

- 当窗口不再处于活动状态时，它们会自动隐藏。

- 只有在明确需要时，例如点击标题栏或可聚焦的视图时，它们才会获得焦点。

- 获得焦点后，可以使用 Esc 键将其关闭。

- 默认情况下，它们不可最小化。

```swift
@main
struct PhotoBrowser: App {
    var body: some Scene {
        WindowGroup {
            PhotoGallery()
        }

        UtilityWindow("Photo Info", id: "photo-info") {
            PhotoInfoViewer()
        }
    }
}

struct PhotoInfoViewer: View {
    // Automatically updates to the photo selection from whichever
    // photo gallery window is focused.
    @FocusedValue(PhotoSelection.self) private var selectedPhotos

    var body: some View {
        Text("\(selectedPhotos.count) photos selected")
    }
}
```

`UtilityWindow` 会自动在“视图”菜单中添加一个菜单项，用于显示/隐藏自身。可以通过将 [commandsRemoved()](scene/commandsRemoved.zh-Hans.md) 应用于实用程序窗口，并在应用程序命令中的其他位置手动添加 [WindowVisibilityToggle](WindowVisibilityToggle.zh-Hans.md) 来移除此功能。实用程序窗口也可以使用 [openWindow](EnvironmentValues/openWindow.zh-Hans.md) 以编程方式显示，并使用 [dismiss](EnvironmentValues/dismiss.zh-Hans.md) 关闭。

## 初始化器

- **init(_:id:content:)**：创建一个带有标题和标识符的实用程序窗口。

## 创建窗口

- **WindowGroup**：一个场景，用于呈现一组结构相同的窗口。

- **Window**：一个场景，将其内容呈现在一个单独的窗口中。

- **WindowStyle**：一个用于定义窗口外观和交互的规范。

- **windowStyle(_:)**：设置此场景创建的窗口的样式。

## 符合以下规范

- 场景


---
source: https://developer.apple.com/documentation/SwiftUI/UtilityWindow
crawled: 2025-12-02T17:21:00Z
---

# UtilityWindow

**Structure**

A specialized window scene that provides secondary utility to the content of the main scenes of an application.

## Declaration

```swift
struct UtilityWindow<Content> where Content : View
```

## Overview

Utility windows are typically used to display controls, settings, or information associated the main content of an application, sometimes referred to as tool palettes or inspector windows. Because of this role, they have specialized behavior compared to all other windows:

- They receive `FocusedValues` from the focused main scene in an application, similar to commands in the main menu, which can be used to display information on the active content as the user focuses on different scenes.
- They have a default window level of `.floating` so they remain visible when moving focus between the main scenes.
- They hide when the window is no longer active.
- They only become focused when explicitly needed, such as clicking in the titlebar or on a focusable view.
- When focused, they can be dismissed with the Escape key.
- They are not minimizable by default.

```swift
@main
struct PhotoBrowser: App {
    var body: some Scene {
        WindowGroup {
            PhotoGallery()
        }

        UtilityWindow("Photo Info", id: "photo-info") {
            PhotoInfoViewer()
        }
    }
}

struct PhotoInfoViewer: View {
    // Automatically updates to the photo selection from whichever
    // photo gallery window is focused.
    @FocusedValue(PhotoSelection.self) private var selectedPhotos

    var body: some View {
        Text("\(selectedPhotos.count) photos selected")
    }
}
```

`UtilityWindow` will automatically add a menu item to show/hide itself in the “View” menu. This can be removed by applying [commandsRemoved()](scene/commandsRemoved.zh-Hans.md) to the utility window, and manually placing a [WindowVisibilityToggle](WindowVisibilityToggle.zh-Hans.md) elsewhere in an app’s commands. Utility windows can also be programmatically presented with [openWindow](EnvironmentValues/openWindow.zh-Hans.md) and dismissed using [dismiss](EnvironmentValues/dismiss.zh-Hans.md).

## Initializers

- **init(_:id:content:)**: Creates a utility window with a title and identifier.

## Creating windows

- **WindowGroup**: A scene that presents a group of identically structured windows.
- **Window**: A scene that presents its content in a single, unique window.
- **WindowStyle**: A specification for the appearance and interaction of a window.
- **windowStyle(_:)**: Sets the style for windows created by this scene.

## Conforms To

- Scene

