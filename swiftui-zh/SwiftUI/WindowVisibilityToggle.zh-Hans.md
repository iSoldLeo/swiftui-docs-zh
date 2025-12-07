--- 来源：https://developer.apple.com/documentation/SwiftUI/WindowVisibilityToggle

抓取时间：2025-12-02T17:21:26Z

---

# WindowVisibilityToggle

**Structure**

一个用于切换窗口可见性的专用按钮。

## 声明

```swift
struct WindowVisibilityToggle<Label> where Label : View
```

## 概述

此按钮最常用于主菜单，它可以切换 `Window` 和 `UtilityWindow` 窗口的可见性。默认标签使用窗口标题，格式为“显示”或“隐藏”，具体取决于窗口的当前可见性。

可以为此按钮分配键盘快捷键。

以下示例演示了如何使用可见性按钮构建主菜单，替换由 `Window` 和 `Utility Window` 添加的默认命令：

```swift
 struct PhotoEditor: App {
     var body: some Scene {
         WindowGroup {
             PhotoEditor()
         }
         .commands {
            CommandGroup(before: .textFormatting) {
                Section {
                    WindowVisibilityToggle(windowID: "formatting")
                        .keyboardShortcut("t", modifiers: [.command, .shift])

                    // other custom/image formatting controls
                }
            }
            CommandGroup(before: .sidebar) {
                Section {
                    WindowVisibilityToggle(windowID: "photo-library")

                    // other controls for showing/hiding UI
                }
            }
         }

         UtilityWindow("Formatting Style", id: "formatting") {
             TextAndImageFormatForm()
         }
         .commandsRemoved()

         Window("Photo Library", id: "photo-library") {
             PhotoInfoViewer()
         }
         .commandsRemoved()
     }
 }
```

## 创建窗口可见性切换按钮

- **init(windowID:)**：创建窗口可见性切换按钮，用于更改特定窗口的可见性。

## 支持的类型

- **DefaultWindowVisibilityToggleLabel**：窗口可见性切换按钮的默认标签。

## 配置窗口可见性

- **defaultLaunchBehavior(_:)**：设置此场景的默认启动行为。

- **restorationBehavior(_:)**：设置此场景的恢复行为。

- **SceneLaunchBehavior**：场景的启动行为。

- **SceneRestorationBehavior**：场景的恢复行为。

- **persistentSystemOverlays(_:)**：设置覆盖在应用程序上的非瞬态系统视图的首选可见性。

- **windowToolbarFullScreenVisibility(_:)**：配置窗口进入全屏模式时窗口工具栏的可见性。

- **WindowToolbarFullScreenVisibility**：窗口工具栏在全屏模式下的可见性。

## 符合

- View


---
source: https://developer.apple.com/documentation/SwiftUI/WindowVisibilityToggle
crawled: 2025-12-02T17:21:26Z
---

# WindowVisibilityToggle

**Structure**

A specialized button for toggling the visibility of a window.

## Declaration

```swift
struct WindowVisibilityToggle<Label> where Label : View
```

## Overview

This is most commonly used in the main menu, where it can toggle the visibility of `Window` and `UtilityWindow` windows. The default label uses the title of the window in the format of “Show ” and “Hide ” depending on the current visibility of the window.

A keyboard shortcut can be assigned to this button.

The below example demonstrates how a main menu can be constructed with visibility buttons, replacing the default commands added by `Window` and `Utility Window`:

```swift
 struct PhotoEditor: App {
     var body: some Scene {
         WindowGroup {
             PhotoEditor()
         }
         .commands {
            CommandGroup(before: .textFormatting) {
                Section {
                    WindowVisibilityToggle(windowID: "formatting")
                        .keyboardShortcut("t", modifiers: [.command, .shift])

                    // other custom/image formatting controls
                }
            }
            CommandGroup(before: .sidebar) {
                Section {
                    WindowVisibilityToggle(windowID: "photo-library")

                    // other controls for showing/hiding UI
                }
            }
         }

         UtilityWindow("Formatting Style", id: "formatting") {
             TextAndImageFormatForm()
         }
         .commandsRemoved()

         Window("Photo Library", id: "photo-library") {
             PhotoInfoViewer()
         }
         .commandsRemoved()
     }
 }
```

## Creating a window visibility toggle

- **init(windowID:)**: Create a window visibility toggle to alter the visibility of a specific window.

## Supporting types

- **DefaultWindowVisibilityToggleLabel**: The default label of a window visibility toggle.

## Configuring window visibility

- **defaultLaunchBehavior(_:)**: Sets the default launch behavior for this scene.
- **restorationBehavior(_:)**: Sets the restoration behavior for this scene.
- **SceneLaunchBehavior**: The launch behavior for a scene.
- **SceneRestorationBehavior**: The restoration behavior for a scene.
- **persistentSystemOverlays(_:)**: Sets the preferred visibility of the non-transient system views overlaying the app.
- **windowToolbarFullScreenVisibility(_:)**: Configures the visibility of the window toolbar when the window enters full screen mode.
- **WindowToolbarFullScreenVisibility**: The visibility of the window toolbar with respect to full screen mode.

## Conforms To

- View

