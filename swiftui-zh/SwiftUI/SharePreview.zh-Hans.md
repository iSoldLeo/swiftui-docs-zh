---
来源： https://developer.apple.com/documentation/SwiftUI/SharePreview
抓取时间： 2025-12-02T17:36:03Z
---

# 分享预览

**Structure**

在共享预览中显示的类型表示。

## 声明

```swift
struct SharePreview<Image, Icon> where Image : Transferable, Icon : Transferable
```

## 概览

在共享系统无法自动预览的内容时使用此类型：

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

您也可以提供预览以加快共享过程。在下面的示例中，预览会立即出现；如果省略预览，系统会通过网络获取链接的元数据：

```swift
ShareLink(
    item: URL(string: "https://developer.apple.com/xcode/swiftui/")!,
    preview: SharePreview(
        "SwiftUI",
        image: Image("SwiftUI"))
```

您可以为`ShareLink` 链接到的项目集合中的每个项目提供唯一的预览：

```swift
ShareLink(items: photos) { photo in
    SharePreview(photo.caption, image: photo.image)
}
```

共享界面决定如何组合这些预览。

每个预览都指定了描述该类型项目的文本和图像。预览的`image` 参数通常是项目的全尺寸表示。例如，如果系统为一个网页链接准备预览，图片可能是该网页上的英雄图片。

预览的`icon`参数通常是项目源的缩略图。例如，如果系统为指向网页的链接准备预览，图标可能是代表网站整体的图像。

系统可以在多个预览中重复使用一个预览表示法，并在每个上下文中显示不同的图像。更多信息和每张图片的推荐尺寸，请参阅 [https://developer.apple.com/library/archive/technotes/tn2444/_index.html]。

## 创建预览

- **init(_:)**：创建预览表示。
- **init(_:image:)**：创建预览表示。
- **init(_:icon:)**：创建预览表示。
- **init(_:image:icon:)**：创建预览表示。

## 链接到其他内容

- **Link**：用于导航到 URL 的控件。
- **ShareLink**：控制共享演示的视图。
- **TextFieldLink**：按下时要求用户输入文本的控件。
- **HelpLink**：具有标准外观的按钮，用于打开特定应用程序的帮助文档。


---
source: https://developer.apple.com/documentation/SwiftUI/SharePreview
crawled: 2025-12-02T17:36:03Z
---

# SharePreview

**Structure**

A representation of a type to display in a share preview.

## Declaration

```swift
struct SharePreview<Image, Icon> where Image : Transferable, Icon : Transferable
```

## Overview

Use this type when sharing content that the system can’t preview automatically:

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

You can also provide a preview to speed up the sharing process. In the following example the preview appears immediately; if you omit the preview instead, the system fetches the link’s metadata over the network:

```swift
ShareLink(
    item: URL(string: "https://developer.apple.com/xcode/swiftui/")!,
    preview: SharePreview(
        "SwiftUI",
        image: Image("SwiftUI"))
```

You can provide unique previews for each item in a collection of items that a `ShareLink` links to:

```swift
ShareLink(items: photos) { photo in
    SharePreview(photo.caption, image: photo.image)
}
```

The share interface decides how to combine those previews.

Each preview specifies text and images that describe an item of the type. The preview’s `image` parameter is typically a full-size representation of the item. For instance, if the system prepares a preview for a link to a webpage, the image might be the hero image on that webpage.

The preview’s `icon` parameter is typically a thumbnail-sized representation of the source of the item. For instance, if the system prepares a preview for a link to a webpage, the icon might be an image that represents the website overall.

The system may reuse a single preview representation for multiple previews, and show different images in each context. For more information and recommended sizes for each image, see [https://developer.apple.com/library/archive/technotes/tn2444/_index.html].

## Creating a preview

- **init(_:)**: Creates a preview representation.
- **init(_:image:)**: Creates a preview representation.
- **init(_:icon:)**: Creates a preview representation.
- **init(_:image:icon:)**: Creates a preview representation.

## Linking to other content

- **Link**: A control for navigating to a URL.
- **ShareLink**: A view that controls a sharing presentation.
- **TextFieldLink**: A control that requests text input from the user when pressed.
- **HelpLink**: A button with a standard appearance that opens app-specific help documentation.

