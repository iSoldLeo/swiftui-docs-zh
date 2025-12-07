--- 来源：https://developer.apple.com/documentation/SwiftUI/Building-and-customizing-the-menu-bar-with-SwiftUI
抓取时间：2025-12-02T15:44:16Z

---

# 使用 SwiftUI 构建和自定义菜单栏

**Article**

通过为 iPadOS 和 macOS 构建原生菜单栏，提供无缝的跨平台用户体验。

## 概述

在 iPadOS 和 macOS 上，菜单栏提供对关键系统操作的访问，例如剪切、复制、粘贴和窗口管理。系统通过菜单栏将这些操作按功能分组到菜单和子菜单中。应用可以添加上下文操作，例如显示和隐藏侧边栏，还可以创建自定义菜单和菜单项，使用户能够从菜单栏执行应用特定的操作。您还可以将菜单栏绑定到键盘快捷键，使您的应用更快更易用。

应用程序包含 [Scene](Scene.zh-Hans.md) 的实例，用于显示应用程序的主要视图。每个场景在菜单栏中提供不同的默认菜单集和操作。与上下文相关的菜单和操作，甚至是自定义菜单和操作，都使用 [commands(content:)](scene/commands_content.zh-Hans.md) 修饰符来指定。

系统提供的菜单和菜单项的顺序在所有应用程序中保持一致，但某些菜单和菜单项会根据上下文添加。例如，基于文档的应用程序会在“文件”菜单中包含用于创建和打开文档的选项。同样，并非所有应用程序都包含文本格式设置功能，但包含文本编辑视图的应用程序会获得一个“格式”菜单，其中包含用于选择字体和设置文本样式的选项，方法是在场景命令中包含 [TextFormattingCommands](TextFormattingCommands.zh-Hans.md)。然后，系统会根据用户在此上下文中的需求添加相应的菜单组和菜单项。

思考用户如何使用您的应用程序，以及哪些操作适合添加到菜单栏，以及应该将它们放置在什么位置。设计指南请参见“人机界面指南”> [doc://com.apple.documentation/design/Human-Interface-Guidelines/the-menu-bar]。

## 填充菜单栏

应用启动时，菜单栏会根据已实现的场景和命令填充菜单和菜单项。条件或上下文相关的命令的菜单项会根据当前激活场景及其视图层级结构的信息动态地激活或禁用。

每个场景都包含一组默认菜单和菜单项，您可以使用 [commands(content:)](scene/commands_content.zh-Hans.md) 修饰符根据应用的特定需求进行补充。

场景的默认菜单和菜单项取决于场景类型支持的功能。例如，[WindowGroup](WindowGroup.zh-Hans.md) 包含用于退出和隐藏应用的命令，以及复制粘贴支持和窗口管理功能。

```swift
@main
struct MyApp: App {
    var body: some Scene {
        WindowGroup {
            ContentView()
        }
    }
}
```

在 macOS 上，[Settings](Settings.zh-Hans.md) 场景包含与 `Window` 相同的操作，但增加了一个用于显示应用“设置”窗口的操作，用户选择“应用菜单”>“设置”即可打开该窗口。在 iPadOS 上，此菜单栏项无需额外的场景，执行后会切换到“设置”应用中的应用设置。

```swift
@main
struct MyApp: App {
    var body: some Scene {
        WindowGroup {
            ContentView()
        }

        #if os(macOS)
        Settings {
            SettingsView()
        }
        #endif
    }
}
```

[DocumentGroup](DocumentGroup.zh-Hans.md) 场景包含 `WindowGroup` 的所有操作，以及一些支持文档管理功能的操作，例如“保存”和“复制”。

将多个场景组合使用，可以创建一个菜单栏，其中包含应用所有核心功能的菜单项，用于创建和编辑文档、管理多个窗口以及显示用户可配置的设置。

```swift
@main
struct MyApp: App {
    var body: some Scene {
        DocumentGroup(newDocument: MyAppDocument()) { file in
            // ...
        }

        #if os(macOS)
        Settings {
            // ...
        }
        #endif
    }
}
```

## 添加系统提供的上下文菜单项

一些常用菜单项是可选的，但如果应用包含某些特定功能，则这些菜单项会很有帮助。例如，并非每个场景都包含导航侧边栏，但对于包含导航侧边栏的场景，用户希望找到一个可以控制导航侧边栏可见性的菜单项。如果您的场景包含导航侧边栏，请使用 [commands(content:)](scene/commands_content.zh-Hans.md) 修饰符并实现 [SidebarCommands](SidebarCommands.zh-Hans.md) 来添加此菜单项：

```swift
@main
struct MyApp: App {
    var body: some Scene {
        DocumentGroup(newDocument: MyAppDocument()) { file in
            ContentView(document: file.$document)
        }
        .commands {
            SidebarCommands()
        }
    }
}
```

有关系统提供的命令组（例如文本格式设置、工具栏和检查器）的更多信息，请参阅 [Commands](Commands.zh-Hans.md)。

## 创建自定义菜单和菜单项

使用 [CommandMenu](CommandMenu.zh-Hans.md) 将应用的自定义菜单项组织并分组到自定义菜单中。系统会将自定义菜单插入到“视图”菜单之后的菜单栏中。

自定义菜单项使用标准的 SwiftUI 视图创建，例如 [Button](Button.zh-Hans.md) 和 [Toggle](Toggle.zh-Hans.md)。[Menu](Menu.zh-Hans.md) 用于创建子菜单。有关菜单项创建的更多信息，请参阅 [doc://com.apple.documentation/documentation/SwiftUI/Populating-SwiftUI-menus-with-adaptive-controls]。

菜单栏还会显示菜单项旁边的键盘快捷键信息，以及用户无需使用菜单栏即可执行操作所需的键盘按键。[keyboardShortcut(_:)](scene/keyboardShortcut.zh-Hans.md) 修饰符允许您定义执行操作的按键组合。请注意，系统提供了许多您的应用无法覆盖的键盘快捷键。有关设计指南，请参阅“人机界面指南”> [doc://com.apple.documentation/design/Human-Interface-Guidelines/keyboards]。

```swift
WindowGroup {
    ContentView()
}
.commands {
    CommandMenu("Actions") {
        Button("Run", systemImage: "play.fill") { ... }
            .keyboardShortcut("R")

        Button("Stop", systemImage: "stop.fill") { ... }
            .keyboardShortcut(".")
    }
}
```

## 修改标准菜单

使用 [CommandGroup](CommandGroup.zh-Hans.md) 修改系统提供的菜单。这些组要么扩展菜单以添加新的菜单项，要么替换指定命令组中的现有菜单项。以这种方式添加菜单项时，您可以根据系统提供的菜单项指定菜单项的位置。

```swift
WindowGroup {
    ContentView()
}
.commands {
    CommandGroup(before: .systemServices) {
        Button("Check for Updates") { ... }
    }
    
    CommandGroup(after: .newItem) {
        Button("New from Clipboard") { ... }
    }
    
    CommandGroup(replacing: .help) {
        Button("User Manual") { ... }
    }
}

```

## 动态更新菜单和菜单项

许多菜单项会根据场景是否处于活动状态、场景是否获得焦点或当前选中的内容来更新其外观或操作。例如，当应用程序的最后一个窗口关闭时，系统会将“文件”菜单中的“关闭窗口”命令置灰。同样，“剪切”和“复制”菜单项仅在用户选择可复制数据时才在活动窗口中可用。此行为也适用于自定义菜单和应用程序提供的菜单项。

使用 [FocusedValue](FocusedValue.zh-Hans.md) 为您的菜单和菜单项创建上下文依赖关系。例如，如果当前焦点位于照片或相册上，则菜单项的标题可以更改。“焦点”值是一种状态数据，它要求当前场景处于活动状态且其视图层次结构处于焦点状态。使用动态属性来响应场景视图的变化。

在以下示例中，一个包含 `WindowGroup` 场景的应用程序，其每个窗口都有一个 [doc://com.apple.documentation/documentation/Observation/Observable()] 数据模型，用于提供该窗口的内容。活动窗口的数据模型通过窗口视图层次结构中的 [focusedSceneValue(_:)](View/focusedSceneValue.zh-Hans.md) 修饰符以焦点值的形式提供。

```swift
@Observable
final class DataModel {
    var messages: [Message]
    ...
}

struct ContentView: View {
    @State private var model = DataModel()

    var body: some View {
        VStack {
            ForEach(model.messages) { ... }
        }
        .focusedSceneValue(model)
    }
}
```

使用 [FocusedValue](FocusedValue.zh-Hans.md) 属性包装器在菜单栏中表示活动场景的数据模型。数据模型会根据“新建消息”按钮的激活状态而改变：

```swift
struct MessageCommands: Commands {
    @FocusedValue(DataModel.self) private var dataModel: DataModel?

    var body: some Commands {
        CommandGroup(after: .newItem) {
            Button("New Message") {
                dataModel?.messages.append(...)
            }
            .disabled(dataModel == nil)
        }
    }
}

@main struct MessagesApp: App {
    var body: some Scene {
        WindowGroup {
            ContentView()
        }
        .commands {
            MessageCommands()
        }
    }
}
```

与 [Environment](Environment.zh-Hans.md) 动态属性类似，`FocusedValue` 使用您提供的键来查找当前值。当焦点值是 `Observable` 对象时，该键可以简单地是对象的类型。

要共享值类型，请使用 [Entry()](Entry.zh-Hans.md) 宏扩展 `FocusedValues` 并添加自定义条目，然后在声明 `FocusedValue` 属性时传递生成的键路径。自定义条目值必须始终是可选的。

```swift
struct ContentView: View {
    @State private var items: [Item] = ...
    @State private var selection: UUID?
    
    var body: some View {
        List(items, selection: $selection) { item in
            ...
        }
        // When active, views in the same scene or in the menu bar
        // can read the selected item ID.
        .focusedSceneValue(\.selectedItemID, selection)
    }
}

struct ItemCommands: Commands {
    @FocusedValue(\.selectedItemID) var selectedItemID: UUID?
    
    var body: some Commands {
        ...
    }
}

extension FocusedValues {
    @Entry var selectedItemID: UUID?
}
```

当菜单项依赖于当前焦点在活动场景视图层次结构中的位置时，请使用 [focusedValue(_:)](View/focusedValue.zh-Hans.md)。这将创建一个焦点值，该值仅在焦点位于修改后的视图或其子视图之一时才对其他视图可见。当焦点位于其他位置时，相应的 `FocusedValue` 属性的值为 `nil`。

```swift
struct ContentView: View {
    @State private var items: [Item] = ...
    @State private var selection: UUID?

    var body: some View {
        NavigationSplitView {
            SidebarContent()
        } detail: {
            List(items, selection: $selection) { item in
                ...
            }

            // The selected item ID is visible when focus is on the 
            // navigation detail list. If focus is on the sidebar, the value of 
            // `@FocusedValue(\.selectedItemID)` is `nil`.
            .focusedValue(\.selectedItemID, selection)
        }
    }
}
```


---
source: https://developer.apple.com/documentation/SwiftUI/Building-and-customizing-the-menu-bar-with-SwiftUI
crawled: 2025-12-02T15:44:16Z
---

# Building and customizing the menu bar with SwiftUI

**Article**

Provide a seamless, cross-platform user experience by building a native menu bar for iPadOS and macOS.

## Overview

On iPadOS and macOS, the menu bar provides access to crucial system-provided actions, such as Cut, Copy, Paste, and window management. The system groups these actions by function into menus and submenus through the menu bar. Apps can add contextual actions, like showing and hiding a sidebar, and can also create custom menus and menu items to allow people to perform app-specific actions from the menu bar. You can also bind menu bar to keyboard shortcuts to make your app quicker and easier to use.



Apps include instances of [Scene](Scene.zh-Hans.md) which display the main views of the app. Each scene provides different default menu sets and actions in the menu bar. Contextually relevant menus and actions, and even custom menus and actions, are specified with the [commands(content:)](scene/commands_content.zh-Hans.md) modifier.

The order of system-provided menus and menu items is consistent across all apps, but some menus and menu items are added depending on context. For example, document-based apps include options in the File menu for creating and opening documents. Similarly, not all apps include text-formatting capabilities, but those that include text editing views get a Format menu with options for choosing fonts and styling text by including [TextFormattingCommands](TextFormattingCommands.zh-Hans.md) in the scene’s commands. The system will then add the appropriate menu groups and items that people expect in this context.

Think about how someone uses your app and which actions make sense to add to the menu bar and where to place them. For design guidance, see Human Interface Guidelines > [doc://com.apple.documentation/design/Human-Interface-Guidelines/the-menu-bar].

## Populate the menu bar

When your app launches, the menu bar populates with menus and menu items based on the implemented scenes and commands. Menu items for conditional or context-dependent commands are made active or inactive dynamically, using information from the active scene and its view hierarchy in focus.

Each scene includes a set of default menus and menu items, which you can supplement with your own app-specific needs using the [commands(content:)](scene/commands_content.zh-Hans.md) modifier.

A scene’s default menus and menu items are dependent on the functionality the scene type supports. For example, [WindowGroup](WindowGroup.zh-Hans.md) includes commands for quitting and hiding the app, as well as Copy and Paste support and window management.

```swift
@main
struct MyApp: App {
    var body: some Scene {
        WindowGroup {
            ContentView()
        }
    }
}
```



On macOS, the [Settings](Settings.zh-Hans.md) scene includes the same actions as `Window`, but adds an action for presenting the app’s Settings window that people get when they choose App menu > Settings. On iPadOS, this menu bar item doesn’t require an additional scene and when performed; it switches to the app’s settings in the Settings app.

```swift
@main
struct MyApp: App {
    var body: some Scene {
        WindowGroup {
            ContentView()
        }

        #if os(macOS)
        Settings {
            SettingsView()
        }
        #endif
    }
}
```



The [DocumentGroup](DocumentGroup.zh-Hans.md) scene includes actions that `WindowGroup` includes, as well as a number of actions that support document management capabilities, like Save and Duplicate.

Using scenes together creates a menu bar that includes menu items for all of the core functionality of an app that creates and edits documents, manages multiple windows, and exposes user-configurable settings.

```swift
@main
struct MyApp: App {
    var body: some Scene {
        DocumentGroup(newDocument: MyAppDocument()) { file in
            // ...
        }

        #if os(macOS)
        Settings {
            // ...
        }
        #endif
    }
}
```

## Add contextual system-provided menu items

Some common menu items are optional, but are helpful if the app contains certain capabilities. For example, not every scene includes a navigation sidebar, but for those that do, people expect to find a menu item that controls the navigation sidebar’s visibility. If your scene includes a navigation sidebar, include this menu item using the [commands(content:)](scene/commands_content.zh-Hans.md) modifier and implementing [SidebarCommands](SidebarCommands.zh-Hans.md):

```swift
@main
struct MyApp: App {
    var body: some Scene {
        DocumentGroup(newDocument: MyAppDocument()) { file in
            ContentView(document: file.$document)
        }
        .commands {
            SidebarCommands()
        }
    }
}
```

For more information on system-provided command groups, such as text formatting, toolbars, and inspectors, see [Commands](Commands.zh-Hans.md).

## Create custom menus and menu items

Organize and group your app’s custom menu items in custom menus using [CommandMenu](CommandMenu.zh-Hans.md). The system inserts custom menus into the menu bar after the View menu.

Custom menu items are created with standard SwiftUI views, for example [Button](Button.zh-Hans.md) and [Toggle](Toggle.zh-Hans.md). [Menu](Menu.zh-Hans.md) creates a submenu. For more information about menu item creation, see [doc://com.apple.documentation/documentation/SwiftUI/Populating-SwiftUI-menus-with-adaptive-controls].

The menu bar also displays information about keyboard shortcuts next to menu items and which keys someone needs to press on the keyboard to perform an action without using the menu bar. The [keyboardShortcut(_:)](scene/keyboardShortcut.zh-Hans.md) modifier allows you to define which key combination will perform the action. Be aware that the system provides many keyboard shortcuts that your app can’t override. For design guidance, see Human Interface Guidelines > [doc://com.apple.documentation/design/Human-Interface-Guidelines/keyboards].

```swift
WindowGroup {
    ContentView()
}
.commands {
    CommandMenu("Actions") {
        Button("Run", systemImage: "play.fill") { ... }
            .keyboardShortcut("R")

        Button("Stop", systemImage: "stop.fill") { ... }
            .keyboardShortcut(".")
    }
}
```



## Modify standard menus

Modify system-provided menus using [CommandGroup](CommandGroup.zh-Hans.md). These groups either extend menus with additional menu items or they replace existing menu items in the indicated command group. When you add menu items in this way, you can specify the location of the menu item based on system-provided menu items.

```swift
WindowGroup {
    ContentView()
}
.commands {
    CommandGroup(before: .systemServices) {
        Button("Check for Updates") { ... }
    }
    
    CommandGroup(after: .newItem) {
        Button("New from Clipboard") { ... }
    }
    
    CommandGroup(replacing: .help) {
        Button("User Manual") { ... }
    }
}

```



## Update menus and menu items dynamically

Many menu items update their appearance or action depending on whether the scene is active, if the scene has focus, or what is currently selected. For example, the system grays out the Close Window command in the File menu when the app’s last window closes. Similarly, the Cut and Copy menu items are only available in the active window if the person selects copyable data. This behavior also applies to custom menus and menu items your app provides.

Use [FocusedValue](FocusedValue.zh-Hans.md) to create contextual dependencies with your menus and menu items. For example, a menu item’s title can change if the current focus is on a photo or a photo album. A focused value is state data that requires an active scene with its view hierarchy in focus. Use a dynamic property to react to changes in the views of the scene.

In the following, an app with a `WindowGroup` scene has an [doc://com.apple.documentation/documentation/Observation/Observable()] data model for each window that supplies that window’s contents. The active window’s data model is made available as a focused value using the [focusedSceneValue(_:)](View/focusedSceneValue.zh-Hans.md) modifier in the window view hierarchy.

```swift
@Observable
final class DataModel {
    var messages: [Message]
    ...
}

struct ContentView: View {
    @State private var model = DataModel()

    var body: some View {
        VStack {
            ForEach(model.messages) { ... }
        }
        .focusedSceneValue(model)
    }
}
```

Use the [FocusedValue](FocusedValue.zh-Hans.md) property wrapper to represent the active scene’s data model in the menu bar. The data model changes whether the “New Message” button is active or inactive:

```swift
struct MessageCommands: Commands {
    @FocusedValue(DataModel.self) private var dataModel: DataModel?

    var body: some Commands {
        CommandGroup(after: .newItem) {
            Button("New Message") {
                dataModel?.messages.append(...)
            }
            .disabled(dataModel == nil)
        }
    }
}

@main struct MessagesApp: App {
    var body: some Scene {
        WindowGroup {
            ContentView()
        }
        .commands {
            MessageCommands()
        }
    }
}
```

Similar to the [Environment](Environment.zh-Hans.md) dynamic property, `FocusedValue` uses a key you provide to find the current value. When the focused value is an `Observable` object, that key can simply be the object’s type.

To share value-typed values, extend `FocusedValues` with a custom entry using the [Entry()](Entry.zh-Hans.md) macro, and pass the resulting key path when declaring the `FocusedValue` property. Custom entry values must always be optional.

```swift
struct ContentView: View {
    @State private var items: [Item] = ...
    @State private var selection: UUID?
    
    var body: some View {
        List(items, selection: $selection) { item in
            ...
        }
        // When active, views in the same scene or in the menu bar
        // can read the selected item ID.
        .focusedSceneValue(\.selectedItemID, selection)
    }
}

struct ItemCommands: Commands {
    @FocusedValue(\.selectedItemID) var selectedItemID: UUID?
    
    var body: some Commands {
        ...
    }
}

extension FocusedValues {
    @Entry var selectedItemID: UUID?
}
```

Use [focusedValue(_:)](View/focusedValue.zh-Hans.md) when a menu item depends on the current placement of focus within the active scene’s view hierarchy. This creates a focused value that’s’ only visible to other views when focus is on the modified view or one of its subviews. When focus is elsewhere, the value of corresponding `FocusedValue` property is `nil`.

```swift
struct ContentView: View {
    @State private var items: [Item] = ...
    @State private var selection: UUID?

    var body: some View {
        NavigationSplitView {
            SidebarContent()
        } detail: {
            List(items, selection: $selection) { item in
                ...
            }

            // The selected item ID is visible when focus is on the 
            // navigation detail list. If focus is on the sidebar, the value of 
            // `@FocusedValue(\.selectedItemID)` is `nil`.
            .focusedValue(\.selectedItemID, selection)
        }
    }
}
```

