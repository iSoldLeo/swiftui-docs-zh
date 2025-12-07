---
来源： https://developer.apple.com/documentation/SwiftUI/ShareLink
抓取时间： 2025-12-02T17:27:51Z
---

# 共享链接

**Structure**

控制共享演示的视图。

## 声明

```swift
struct ShareLink<Data, PreviewImage, PreviewIcon, Label> where Data : RandomAccessCollection, PreviewImage : Transferable, PreviewIcon : Transferable, Label : View, Data.Element : Transferable
```

## 概览

人们点击或单击分享链接，就会出现一个分享界面。该链接通常使用系统标准外观；您只需提供要共享的内容：

```swift
ShareLink(item: URL(string: "https://developer.apple.com/xcode/swiftui/")!)
```

您可以通过提供视图内容来控制链接的外观。例如，您可以使用[Label](Label.zh-Hans.md) 显示带有自定义图标的链接：

```swift
ShareLink(item: URL(string: "https://developer.apple.com/xcode/swiftui/")!) {
    Label("Share", image: "MyCustomShareIcon")
}
```

如果您只想自定义链接的标题，可以使用其中一个方便的初始化程序，它可以接收一个字符串并为您创建一个 `Label`：

```swift
ShareLink("Share URL", item: URL(string: "https://developer.apple.com/xcode/swiftui/")!)
```

链接可以共享[doc://com.apple.documentation/documentation/CoreTransferable/Transferable]的任何内容。许多框架类型，如[doc://com.apple.documentation/documentation/Foundation/URL]，都已符合此协议。您也可以使自己的类型具有可转移性。

例如，您可以使用 [doc://com.apple.documentation/documentation/CoreTransferable/ProxyRepresentation] 将自己的类型解析为框架类型：

```swift
struct Photo: Transferable {
    static var transferRepresentation: some TransferRepresentation {
        ProxyRepresentation(\.image)
    }

    public var image: Image
    public var caption: String
}

struct PhotoView: View {
    let photo: Photo

    var body: View {
        photo.image
            .toolbar {
                ShareLink(
                    item: photo,
                    preview: SharePreview(
                        photo.caption,
                        image: photo.image))
            }
    }
}
```

有时，您的应用程序共享的内容并不是立即可用的。当您需要异步操作（如网络请求）来检索和准备内容时，可以使用[doc://com.apple.documentation/documentation/CoreTransferable/FileRepresentation] 或 [doc://com.apple.documentation/documentation/CoreTransferable/DataRepresentation]。

请注意，有些应用程序提供文件共享服务，但不提供多种不同数据类型的共享服务，例如 Mail.app、Notes.app、Messages.app 或 AirDrop。如果在显示的 `ShareLink`中没有看到特定的共享服务，请尝试在该类型的 `Transferable` 一致性中添加 [doc://com.apple.documentation/documentation/CoreTransferable/FileRepresentation]。

一个`Transferable`类型还可以为一个可共享项目提供多种内容类型。共享界面会根据您提供的类型显示相关的共享服务。

上一个示例还显示了如何在共享界面中显示内容预览。

共享 URL 或非归属字符串时不需要预览。共享这些类型的内容时，系统会自动确定预览。

即使是可选的预览，也可以提供。例如，在共享 URL 时，自动预览首先会在基本 URL 旁显示一个占位符链接图标，同时通过网络获取链接的元数据。一旦链接图标和标题可用，预览就会更新。如果你提供的是预览，预览会立即显示，而不会通过网络获取数据。

某些共享活动支持主题和信息字段。您可以使用 `subject` 和 `message` 参数预填充这些字段：

```swift
ShareLink(
    item: photo,
    subject: Text("Cool Photo"),
    message: Text("Check it out!")
    preview: SharePreview(
        photo.caption,
        image: photo.image))
```参数

## 共享一个项目

- **init(item:subject:message:)**：创建一个显示共享界面的实例。
- **init(_:item:subject:message:)**：创建一个带有自定义标签的实例，用于显示共享界面。
- **init(item:subject:message:label:)**：创建显示共享界面的实例。

## 通过预览共享项目

- **init(item:subject:message:preview:)**：创建一个显示共享界面的实例。
- **init(_:item:subject:message:preview:)**：创建一个带有自定义标签的实例，用于显示共享界面。
- **init(item:subject:message:preview:label:)**：创建显示共享界面的实例。

## 共享项目

- **init(items:subject:message:)**：创建显示共享界面的实例。
- **init(_:items:subject:message:)**：创建一个带有自定义标签的实例，用于显示共享界面。
- **init(items:subject:message:label:)**：创建显示共享界面的实例。

## 带预览的共享项目

- **init(items:subject:message:preview:)**：创建一个显示共享界面的实例。
- **init(_:items:subject:message:preview:)**：创建一个带有自定义标签的实例，用于显示共享界面。
- **init(items:subject:message:preview:label:)**：创建一个显示共享界面的实例。

## 支持类型

- **DefaultShareLinkLabel**：共享链接使用的默认标签。

## 链接到其他内容

- **Link**：用于导航到 URL 的控件。
- **SharePreview**：在共享预览中显示的类型表示。
- **TextFieldLink**：按下时要求用户输入文本的控件。
- **HelpLink**：具有标准外观的按钮，用于打开特定应用程序的帮助文档。

## 符合

- 查看


---
source: https://developer.apple.com/documentation/SwiftUI/ShareLink
crawled: 2025-12-02T17:27:51Z
---

# ShareLink

**Structure**

A view that controls a sharing presentation.

## Declaration

```swift
struct ShareLink<Data, PreviewImage, PreviewIcon, Label> where Data : RandomAccessCollection, PreviewImage : Transferable, PreviewIcon : Transferable, Label : View, Data.Element : Transferable
```

## Overview

People tap or click on a share link to present a share interface. The link typically uses a system-standard appearance; you only need to supply the content to share:

```swift
ShareLink(item: URL(string: "https://developer.apple.com/xcode/swiftui/")!)
```

You can control the appearance of the link by providing view content. For example, you can use a [Label](Label.zh-Hans.md) to display a link with a custom icon:

```swift
ShareLink(item: URL(string: "https://developer.apple.com/xcode/swiftui/")!) {
    Label("Share", image: "MyCustomShareIcon")
}
```

If you only wish to customize the link’s title, you can use one of the convenience initializers that takes a string and creates a `Label` for you:

```swift
ShareLink("Share URL", item: URL(string: "https://developer.apple.com/xcode/swiftui/")!)
```

The link can share any content that is [doc://com.apple.documentation/documentation/CoreTransferable/Transferable]. Many framework types, like [doc://com.apple.documentation/documentation/Foundation/URL], already conform to this protocol. You can also make your own types transferable.

For example, you can use [doc://com.apple.documentation/documentation/CoreTransferable/ProxyRepresentation] to resolve your own type to a framework type:

```swift
struct Photo: Transferable {
    static var transferRepresentation: some TransferRepresentation {
        ProxyRepresentation(\.image)
    }

    public var image: Image
    public var caption: String
}

struct PhotoView: View {
    let photo: Photo

    var body: View {
        photo.image
            .toolbar {
                ShareLink(
                    item: photo,
                    preview: SharePreview(
                        photo.caption,
                        image: photo.image))
            }
    }
}
```

Sometimes the content that your app shares isn’t immediately available. You can use [doc://com.apple.documentation/documentation/CoreTransferable/FileRepresentation] or [doc://com.apple.documentation/documentation/CoreTransferable/DataRepresentation] when you need an asynchronous operation, like a network request, to retrieve and prepare the content.

Note that some applications offer their sharing service for files, but not for a wide range of different data types, for example, Mail.app, Notes.app, Messages.app or AirDrop. If you don’t see a particular sharing service in the presented `ShareLink`, try adding a [doc://com.apple.documentation/documentation/CoreTransferable/FileRepresentation] to the type’s `Transferable` conformance.

A `Transferable` type also lets you provide multiple content types for a single shareable item. The share interface shows relevant sharing services based on the types that you provide.

The previous example also shows how you provide a preview of your content to show in the share interface.

A preview isn’t required when sharing URLs or non-attributed strings. When sharing these types of content, the system can automatically determine a preview.

You can provide a preview even when it’s optional. For instance, when sharing URLs, the automatic preview first shows a placeholder link icon alongside the base URL while fetching the link’s metadata over the network. The preview updates once the link’s icon and title become available. If you provide a preview instead, the preview appears immediately without fetching data over the network.

Some share activities support subject and message fields. You can pre-populate these fields with the `subject` and `message` parameters:

```swift
ShareLink(
    item: photo,
    subject: Text("Cool Photo"),
    message: Text("Check it out!")
    preview: SharePreview(
        photo.caption,
        image: photo.image))
```

## Sharing an item

- **init(item:subject:message:)**: Creates an instance that presents the share interface.
- **init(_:item:subject:message:)**: Creates an instance, with a custom label, that presents the share interface.
- **init(item:subject:message:label:)**: Creates an instance that presents the share interface.

## Sharing an item with a preview

- **init(item:subject:message:preview:)**: Creates an instance that presents the share interface.
- **init(_:item:subject:message:preview:)**: Creates an instance, with a custom label, that presents the share interface.
- **init(item:subject:message:preview:label:)**: Creates an instance that presents the share interface.

## Sharing items

- **init(items:subject:message:)**: Creates an instance that presents the share interface.
- **init(_:items:subject:message:)**: Creates an instance, with a custom label, that presents the share interface.
- **init(items:subject:message:label:)**: Creates an instance that presents the share interface.

## Sharing items with a preview

- **init(items:subject:message:preview:)**: Creates an instance that presents the share interface.
- **init(_:items:subject:message:preview:)**: Creates an instance, with a custom label, that presents the share interface.
- **init(items:subject:message:preview:label:)**: Creates an instance that presents the share interface.

## Supporting types

- **DefaultShareLinkLabel**: The default label used for a share link.

## Linking to other content

- **Link**: A control for navigating to a URL.
- **SharePreview**: A representation of a type to display in a share preview.
- **TextFieldLink**: A control that requests text input from the user when pressed.
- **HelpLink**: A button with a standard appearance that opens app-specific help documentation.

## Conforms To

- View

