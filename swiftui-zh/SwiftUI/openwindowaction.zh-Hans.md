--- 来源：https://developer.apple.com/documentation/swiftui/openwindowaction
抓取时间：2025-12-04T11:27:50Z

---

# OpenWindowAction

**Structure**

一个用于显示窗口的操作。

## 声明

```swift
@MainActor @preconcurrency struct OpenWindowAction
```

## 概述

使用 [openWindow](EnvironmentValues/openWindow.zh-Hans.md) 环境变量值获取给定 [Environment](Environment.zh-Hans.md) 对应的此结构实例。然后调用该实例来打开窗口。之所以直接调用实例，是因为它定义了一个 [callAsFunction(id:)](OpenWindowAction/callAsFunction_id.zh-Hans.md) 方法，Swift 会在调用实例时调用该方法。

例如，您可以定义一个按钮，用于打开一个新的邮件查看器窗口：

```swift
@main
struct Mail: App {
    var body: some Scene {
        WindowGroup(id: "mail-viewer") {
            MailViewer()
        }
    }
}

struct NewViewerButton: View {
    @Environment(\.openWindow) private var openWindow

    var body: some View {
        Button("Open new mail viewer") {
            openWindow(id: "mail-viewer")
        }
    }
}
```

您可以通过提供以下选项之一来指定要打开的场景：

- 一个字符串标识符，通过 `id` 参数传递，如上例所示。

- 一个 `value` 参数，其类型与您在场景初始化程序中指定的类型匹配。

- 同时提供标识符和值。这样，您可以定义多个窗口组，这些窗口组接受相同类型的输入值，例如 [doc://com.apple.documentation/documentation/Foundation/UUID]。

使用第一个选项可以定位应用程序中具有匹配标识符的 [WindowGroup](WindowGroup.zh-Hans.md) 或 [Window](Window.zh-Hans.md) 场景。对于 `WindowGroup`，系统会为该组创建一个新窗口。如果窗口组显示数据，系统会将默认值或 `nil` 提供给窗口的根视图。如果目标场景是 `Window`，系统会将其置于最前。

使用其他两个选项可以指定目标场景为 `WindowGroup` 并提供要显示的值。如果界面中已存在来自该窗口组且显示指定值的窗口，系统会将该窗口置于最前。否则，系统会创建一个新窗口，并将绑定传递给指定值。

## 调用操作

- **callAsFunction(id:)**：打开与指定标识符关联的窗口。

- **callAsFunction(id:value:)**：打开由窗口组定义且显示指定值类型并与指定标识符关联的窗口。

- **callAsFunction(value:)**：打开一个由窗口组定义的窗口，该窗口组显示指定值的类型。

## 结构

- **OpenWindowAction.SharingBehavior**

## 实例方法

- **callAsFunction(id:sharingBehavior:)**：打开一个与指定标识符关联的窗口，并使用指定的共享行为。

- **callAsFunction(id:value:sharingBehavior:)**：打开一个由窗口组定义的窗口，该窗口组显示指定值的类型，并且与指定标识符关联，并使用指定的共享行为。

- **callAsFunction(value:sharingBehavior:)**：打开一个由窗口组定义的窗口，该窗口组显示指定值的类型，并使用指定的共享行为。

## 打开窗口

- **显示窗口和空间**：打开和关闭构成应用程序界面的场景。

- **supportsMultipleWindows**：一个布尔值，指示当前平台是否支持打开多个窗口。

- **openWindow**：存储在视图环境中的窗口呈现操作。

- **PushWindowAction**：一个用于在调用该操作的窗口之外打开请求窗口的操作。

## 符合以下标准

- Sendable

- SendableMetatype


---
source: https://developer.apple.com/documentation/swiftui/openwindowaction
crawled: 2025-12-04T11:27:50Z
---

# OpenWindowAction

**Structure**

An action that presents a window.

## Declaration

```swift
@MainActor @preconcurrency struct OpenWindowAction
```

## Overview

Use the [openWindow](EnvironmentValues/openWindow.zh-Hans.md) environment value to get the instance of this structure for a given [Environment](Environment.zh-Hans.md). Then call the instance to open a window. You call the instance directly because it defines a [callAsFunction(id:)](OpenWindowAction/callAsFunction_id.zh-Hans.md) method that Swift calls when you call the instance.

For example, you can define a button that opens a new mail viewer window:

```swift
@main
struct Mail: App {
    var body: some Scene {
        WindowGroup(id: "mail-viewer") {
            MailViewer()
        }
    }
}

struct NewViewerButton: View {
    @Environment(\.openWindow) private var openWindow

    var body: some View {
        Button("Open new mail viewer") {
            openWindow(id: "mail-viewer")
        }
    }
}
```

You indicate which scene to open by providing one of the following:

- A string identifier that you pass through the `id` parameter, as in the above example.
- A `value` parameter that has a type that matches the type that you specify in the scene’s initializer.
- Both an identifier and a value. This enables you to define multiple window groups that take input values of the same type, like a [doc://com.apple.documentation/documentation/Foundation/UUID].

Use the first option to target either a [WindowGroup](WindowGroup.zh-Hans.md) or a [Window](Window.zh-Hans.md) scene in your app that has a matching identifier. For a `WindowGroup`, the system creates a new window for the group. If the window group presents data, the system provides the default value or `nil` to the window’s root view. If the targeted scene is a `Window`, the system orders it to the front.

Use the other two options to target a `WindowGroup` and provide a value to present. If the interface already has a window from the group that’s presenting the specified value, the system brings the window to the front. Otherwise, the system creates a new window and passes a binding to the specified value.

## Calling the action

- **callAsFunction(id:)**: Opens a window that’s associated with the specified identifier.
- **callAsFunction(id:value:)**: Opens a window defined by the window group that presents the specified value type and that’s associated with the specified identifier.
- **callAsFunction(value:)**: Opens a window defined by a window group that presents the type of the specified value.

## Structures

- **OpenWindowAction.SharingBehavior**

## Instance Methods

- **callAsFunction(id:sharingBehavior:)**: Opens a window that’s associated with the specified identifier, using the specified sharing sharingBehavior..
- **callAsFunction(id:value:sharingBehavior:)**: Opens a window defined by the window group that presents the specified value type and that’s associated with the specified identifier, using the specified sharingBehavior.
- **callAsFunction(value:sharingBehavior:)**: Opens a window defined by a window group that presents the type of the specified value, using the specified sharingBehavior.

## Opening windows

- **Presenting windows and spaces**: Open and close the scenes that make up your app’s interface.
- **supportsMultipleWindows**: A Boolean value that indicates whether the current platform supports opening multiple windows.
- **openWindow**: A window presentation action stored in a view’s environment.
- **PushWindowAction**: An action that opens the requested window in place of the window the action is called from.

## Conforms To

- Sendable
- SendableMetatype

