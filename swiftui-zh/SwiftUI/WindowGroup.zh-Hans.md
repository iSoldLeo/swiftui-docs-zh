--- 来源：https://developer.apple.com/documentation/SwiftUI/WindowGroup

抓取时间：2025-12-02T16:23:19Z

---

# WindowGroup

**Structure**

一个用于呈现一组结构相同的窗口的场景。

## 声明

```swift
struct WindowGroup<Content> where Content : View
```

## 概述

使用 `WindowGroup` 作为应用程序呈现的视图层级结构的容器。您声明为组内容的层级结构将作为应用程序从该组创建的每个窗口的模板：

```swift
@main
struct Mail: App {
    var body: some Scene {
        WindowGroup {
            MailViewer() // Define a view hierarchy for the window.
        }
    }
}
```

SwiftUI 会处理某些平台特定的行为。例如，在 macOS 和 iPadOS 等支持的平台上，用户可以同时打开组中的多个窗口。在 macOS 中，用户可以将打开的窗口集中到一个标签式界面中。在 macOS 中，窗口组会自动提供用于标准窗口管理的命令。

组中的每个窗口都保持独立的状态。例如，系统会为它创建的每个窗口分配新的存储空间，用于存储场景视图层级中实例化的任何 [State](State.zh-Hans.md) 或 [StateObject](StateObject.zh-Hans.md) 变量。

对于基于文档的应用程序，请使用 [DocumentGroup](DocumentGroup.zh-Hans.md) 来定义窗口。

### 以编程方式打开窗口

如果您使用标识符、显示类型或两者初始化窗口组，则可以以编程方式从该组中打开窗口。例如，您可以为上例中的邮件查看器场景指定一个标识符：

```swift
WindowGroup(id: "mail-viewer") { // Identify the window group.
    MailViewer()
}
```

在代码的其他位置，您可以使用环境中的 [openWindow](EnvironmentValues/openWindow.zh-Hans.md) 操作从该组创建一个新窗口：

```swift
struct NewViewerButton: View {
    @Environment(\.openWindow) private var openWindow

    var body: some View {
        Button("Open new mail viewer") {
            openWindow(id: "mail-viewer") // Match the group's identifier.
        }
    }
}
```

请确保为应用中应用于窗口组的标识符使用唯一的字符串。

### 在窗口中显示数据

如果您使用呈现类型初始化窗口组，则可以在打开窗口时将该类型的数据传递给它。例如，您可以为邮件应用定义第二个窗口组，用于显示指定的邮件：

```swift
@main
struct Mail: App {
    var body: some Scene {
        WindowGroup {
            MailViewer(id: "mail-viewer")
        }

        // A window group that displays messages.
        WindowGroup(for: Message.ID.self) { $messageID in
            MessageDetail(messageID: messageID)
        }
    }
}
```

当您使用值调用 [openWindow](EnvironmentValues/openWindow.zh-Hans.md) 操作时，SwiftUI 会找到具有匹配类型的窗口组，并将该值的绑定传递到窗口组的内容闭包中。例如，您可以定义一个按钮，通过传递消息的标识符来打开消息：

```swift
struct NewMessageButton: View {
    var message: Message
    @Environment(\.openWindow) private var openWindow

    var body: some View {
        Button("Open message") {
            openWindow(value: message.id)
        }
    }
}
```

请确保您呈现的类型同时符合 [doc://com.apple.documentation/documentation/Swift/Hashable] 和 [doc://com.apple.documentation/documentation/Swift/Codable] 协议。此外，呈现值最好使用轻量级数据。对于符合 [doc://com.apple.documentation/documentation/Swift/Identifiable] 协议的模型值，其标识符可以很好地用作呈现类型，如上例所示。

如果用户界面中已存在一个窗口绑定到与您传递给 `openWindow` 操作的值相同的值，则系统会将现有窗口置于最前，而不是打开一个新窗口。如果 SwiftUI 没有值可供提供（例如，当用户通过 macOS 菜单栏选择“文件”>“新建窗口”打开窗口时），SwiftUI 会改为传递绑定到 `nil` 值的值。为避免收到 `nil` 值，您可以选择在窗口组初始化器中指定默认值。例如，对于消息查看器，您可以显示一条新的空消息：

```swift
WindowGroup(for: Message.ID.self) { $messageID in
    MessageDetail(messageID: messageID)
} defaultValue: {
    model.makeNewMessage().id // A new message that your model stores.
}
```

SwiftUI 会持久化绑定值以用于状态恢复，并在恢复窗口时重新应用相同的值。如果恢复过程出错，SwiftUI 会将绑定值设置为您提供的默认值，否则设置为 `nil`。

### 为应用的窗口命名

为了帮助用户区分不同组的窗口，请在组初始化器中将标题作为第一个参数：

```swift
WindowGroup("Message", for: Message.ID.self) { $messageID in
    MessageDetail(messageID: messageID)
}
```

SwiftUI 在以下情况下使用此标题来引用窗口：

- 用户可以使用“文件”>“新建”菜单打开的新窗口列表。

- 窗口的标题栏。

- “窗口”菜单显示的已打开窗口列表。

如果您未为窗口提供标题，系统将使用应用程序的名称来指代该窗口。

### 区分呈现相同数据的窗口

要以编程方式区分呈现相同类型数据的窗口（例如，当您使用 [doc://com.apple.documentation/documentation/Foundation/UUID] 作为多个模型类型的标识符时），请将 `id` 参数添加到组的初始化程序中，以提供唯一的字符串标识符：

```swift
WindowGroup("Message", id: "message", for: UUID.self) { $uuid in
    MessageDetail(uuid: uuid)
}
WindowGroup("Account", id: "account-info", for: UUID.self) { $uuid in
    AccountDetail(uuid: uuid)
}
```

然后，使用标识符和值来打开窗口：

```swift
struct ActionButtons: View {
    var messageID: UUID
    var accountID: UUID

    @Environment(\.openWindow) private var openWindow

    var body: some View {
        HStack {
            Button("Open message") {
                openWindow(id: "message", value: messageID)
            }
            Button("Edit account information") {
                openWindow(id: "account-info", value: accountID)
            }
        }
    }
}
```

### 以编程方式关闭窗口

系统为用户提供了适用于不同平台的控件来关闭窗口。您还可以通过从窗口的视图层次结构中调用 [dismiss](EnvironmentValues/dismiss.zh-Hans.md) 操作来以编程方式关闭窗口。例如，您可以在上例中的账户详情视图中添加一个按钮来关闭该视图：

```swift
struct AccountDetail: View {
    var uuid: UUID?
    @Environment(\.dismiss) private var dismiss

    var body: some View {
        VStack {
            // ...

            Button("Dismiss") {
                dismiss()
            }
        }
    }
}
```

如果您从窗口显示的模态框（例如表格或弹出框）中调用此关闭操作，则该操作不会关闭窗口。在这种情况下，该操作会关闭模态框。

## 创建窗口组

- **init(content:)**：创建窗口组。

- **init(_:content:)**：创建带有文本视图标题的窗口组。

## 标识窗口组

- **init(id:content:)**：创建带有标识符的窗口组。

- **init(_:id:content:)**：创建带有文本视图标题和标识符的窗口组。

## 创建数据驱动窗口组

- **init(for:content:)**：创建数据呈现窗口组。

- **init(_:for:content:)**：创建带有文本视图标题的数据呈现窗口组。

## 为窗口组提供默认数据

- **init(for:content:defaultValue:)**：创建带有默认值的数据呈现窗口组。

- **init(_:for:content:defaultValue:)**：创建带有文本视图标题和默认值的数据呈现窗口组。

## 标识数据驱动窗口组

- **init(id:for:content:)**：创建带有标识符的数据呈现窗口组。

- **init(_:id:for:content:)**：创建带有文本视图标题和标识符的数据呈现窗口组。

## 标识具有默认数据的窗口组

- **init(id:for:content:defaultValue:)**：创建一个包含标识符和默认值的数据展示窗口组。

- **init(_:id:for:content:defaultValue:)**：创建一个包含文本视图标题、标识符和默认值的数据展示窗口组。

## 支持的类型

- **PresentedWindowContent**：表示已展示窗口内容的视图。

## 初始化器

- **init(_:id:makeContent:)**：创建一个包含文本视图标题和标识符的窗口组。

- **init(_:makeContent:)**：创建一个包含文本视图标题的窗口组。

- **init(id:makeContent:)**：创建一个包含标识符的窗口组。

- **init(makeContent:)**：创建一个窗口组。

## 创建窗口

- **Window**：一个场景，其内容在一个独立的窗口中呈现。

- **UtilityWindow**：一个专门的窗口场景，为应用程序的主场景内容提供辅助功能。

- **WindowStyle**：窗口外观和交互的规范。

- **windowStyle(_:)**：设置此场景创建的窗口的样式。

## 符合以下规范

- 场景


---
source: https://developer.apple.com/documentation/SwiftUI/WindowGroup
crawled: 2025-12-02T16:23:19Z
---

# WindowGroup

**Structure**

A scene that presents a group of identically structured windows.

## Declaration

```swift
struct WindowGroup<Content> where Content : View
```

## Overview

Use a `WindowGroup` as a container for a view hierarchy that your app presents. The hierarchy that you declare as the group’s content serves as a template for each window that the app creates from that group:

```swift
@main
struct Mail: App {
    var body: some Scene {
        WindowGroup {
            MailViewer() // Define a view hierarchy for the window.
        }
    }
}
```

SwiftUI takes care of certain platform-specific behaviors. For example, on platforms that support it, like macOS and iPadOS, people can open more than one window from the group simultaneously. In macOS, people can gather open windows together in a tabbed interface. Also in macOS, window groups automatically provide commands for standard window management.



Every window in the group maintains independent state. For example, the system allocates new storage for any [State](State.zh-Hans.md) or [StateObject](StateObject.zh-Hans.md) variables instantiated by the scene’s view hierarchy for each window that it creates.

For document-based apps, use [DocumentGroup](DocumentGroup.zh-Hans.md) to define windows instead.

### Open windows programmatically

If you initialize a window group with an identifier, a presentation type, or both, you can programmatically open a window from the group. For example, you can give the mail viewer scene from the previous example an identifier:

```swift
WindowGroup(id: "mail-viewer") { // Identify the window group.
    MailViewer()
}
```

Elsewhere in your code, you can use the [openWindow](EnvironmentValues/openWindow.zh-Hans.md) action from the environment to create a new window from the group:

```swift
struct NewViewerButton: View {
    @Environment(\.openWindow) private var openWindow

    var body: some View {
        Button("Open new mail viewer") {
            openWindow(id: "mail-viewer") // Match the group's identifier.
        }
    }
}
```

Be sure to use unique strings for identifiers that you apply to window groups in your app.

### Present data in a window

If you initialize a window group with a presentation type, you can pass data of that type to the window when you open it. For example, you can define a second window group for the Mail app that displays a specified message:

```swift
@main
struct Mail: App {
    var body: some Scene {
        WindowGroup {
            MailViewer(id: "mail-viewer")
        }

        // A window group that displays messages.
        WindowGroup(for: Message.ID.self) { $messageID in
            MessageDetail(messageID: messageID)
        }
    }
}
```

When you call the [openWindow](EnvironmentValues/openWindow.zh-Hans.md) action with a value, SwiftUI finds the window group with the matching type and passes a binding to the value into the window group’s content closure. For example, you can define a button that opens a message by passing the message’s identifier:

```swift
struct NewMessageButton: View {
    var message: Message
    @Environment(\.openWindow) private var openWindow

    var body: some View {
        Button("Open message") {
            openWindow(value: message.id)
        }
    }
}
```

Be sure that the type you present conforms to both the [doc://com.apple.documentation/documentation/Swift/Hashable] and [doc://com.apple.documentation/documentation/Swift/Codable] protocols. Also, prefer lightweight data for the presentation value. For model values that conform to the [doc://com.apple.documentation/documentation/Swift/Identifiable] protocol, the value’s identifier works well as a presentation type, as the above example demonstrates.

If a window with a binding to the same value that you pass to the `openWindow` action already appears in the user interface, the system brings the existing window to the front rather than opening a new window. If SwiftUI doesn’t have a value to provide — for example, when someone opens a window by choosing File > New Window from the macOS menu bar — SwiftUI passes a binding to a `nil` value instead. To avoid receiving a `nil` value, you can optionally specify a default value in your window group initializer. For example, for the message viewer, you can present a new empty message:

```swift
WindowGroup(for: Message.ID.self) { $messageID in
    MessageDetail(messageID: messageID)
} defaultValue: {
    model.makeNewMessage().id // A new message that your model stores.
}
```

SwiftUI persists the value of the binding for the purposes of state restoration, and reapplies the same value when restoring the window. If the restoration process results in an error, SwiftUI sets the binding to the default value if you provide one, or `nil` otherwise.

### Title your app’s windows

To help people distinguish among windows from different groups, include a title as the first parameter in the group’s initializer:

```swift
WindowGroup("Message", for: Message.ID.self) { $messageID in
    MessageDetail(messageID: messageID)
}
```

SwiftUI uses this title when referring to the window in:

- The list of new windows that someone can open using the File > New menu.
- The window’s title bar.
- The list of open windows that the Window menu displays.

If you don’t provide a title for a window, the system refers to the window using the app’s name instead.



### Distinguish windows that present like data

To programmatically distinguish between windows that present the same type of data, like when you use a [doc://com.apple.documentation/documentation/Foundation/UUID] as the identifier for more than one model type, add the `id` parameter to the group’s initializer to provide a unique string identifier:

```swift
WindowGroup("Message", id: "message", for: UUID.self) { $uuid in
    MessageDetail(uuid: uuid)
}
WindowGroup("Account", id: "account-info", for: UUID.self) { $uuid in
    AccountDetail(uuid: uuid)
}
```

Then use both the identifer and a value to open the window:

```swift
struct ActionButtons: View {
    var messageID: UUID
    var accountID: UUID

    @Environment(\.openWindow) private var openWindow

    var body: some View {
        HStack {
            Button("Open message") {
                openWindow(id: "message", value: messageID)
            }
            Button("Edit account information") {
                openWindow(id: "account-info", value: accountID)
            }
        }
    }
}
```

### Dismiss a window programmatically

The system provides people with platform-appropriate controls to dismiss a window. You can also dismiss windows programmatically by calling the [dismiss](EnvironmentValues/dismiss.zh-Hans.md) action from within the window’s view hierarchy. For example, you can include a button in the account detail view from the previous example that dismisses the view:

```swift
struct AccountDetail: View {
    var uuid: UUID?
    @Environment(\.dismiss) private var dismiss

    var body: some View {
        VStack {
            // ...

            Button("Dismiss") {
                dismiss()
            }
        }
    }
}
```

The dismiss action doesn’t close the window if you call it from a modal — like a sheet or a popover — that you present from the window. In that case, the action dismisses the modal presentation instead.

## Creating a window group

- **init(content:)**: Creates a window group.
- **init(_:content:)**: Creates a window group with a text view title.

## Identifying a window group

- **init(id:content:)**: Creates a window group with an identifier.
- **init(_:id:content:)**: Creates a window group with a text view title and an identifier.

## Creating a data-driven window group

- **init(for:content:)**: Creates a data-presenting window group.
- **init(_:for:content:)**: Creates a data-presenting window group with a text view title.

## Providing default data to a window group

- **init(for:content:defaultValue:)**: Creates a data-presenting window group with a default value.
- **init(_:for:content:defaultValue:)**: Creates a data-presenting window group with a text view title and a default value.

## Identifying a data-driven window group

- **init(id:for:content:)**: Creates a data-presenting window group with an identifier.
- **init(_:id:for:content:)**: Creates a data-presenting window group with a text view title and an identifier.

## Identifying a window group that has default data

- **init(id:for:content:defaultValue:)**: Creates a data-presenting window group with an identifier and a default value.
- **init(_:id:for:content:defaultValue:)**: Creates a data-presenting window group with a text view title, an identifier, and a default value.

## Supporting types

- **PresentedWindowContent**: A view that represents the content of a presented window.

## Initializers

- **init(_:id:makeContent:)**: Creates a window group with a text view title and an identifier.
- **init(_:makeContent:)**: Creates a window group with a text view title.
- **init(id:makeContent:)**: Creates a window group with an identifier.
- **init(makeContent:)**: Creates a window group.

## Creating windows

- **Window**: A scene that presents its content in a single, unique window.
- **UtilityWindow**: A specialized window scene that provides secondary utility to the content of the main scenes of an application.
- **WindowStyle**: A specification for the appearance and interaction of a window.
- **windowStyle(_:)**: Sets the style for windows created by this scene.

## Conforms To

- Scene

