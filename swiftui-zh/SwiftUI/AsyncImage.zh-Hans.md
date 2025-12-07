---
来源： https://developer.apple.com/documentation/SwiftUI/AsyncImage
抓取时间： 2025-12-02T17:04:42Z
---

# AsyncImage

**Structure**

异步加载并显示图像的视图。

## 声明

```swift
struct AsyncImage<Content> where Content : View
```

## 概览

该视图使用共享的 [doc://com.apple.documentation/documentation/Foundation/URLSession] 实例从指定的 URL 加载图像，然后显示图像。例如，您可以显示存储在服务器上的图标：

```swift
AsyncImage(url: URL(string: "https://example.com/icon.png"))
    .frame(width: 200, height: 200)
```

在图片加载之前，视图会显示一个标准占位符，占满可用空间。加载成功后，视图会更新以显示图像。在上面的示例中，图标小于框架，因此显示的图标小于占位符。



您可以使用 [init(url:scale:content:placeholder:)](AsyncImage/init_url_scale_content_placeholder.zh-Hans.md) 指定自定义占位符。有了这个初始化程序，您还可以使用`content` 参数来操作加载的图像。例如，您可以添加一个修改器，使加载的图像可以调整大小：

```swift
AsyncImage(url: URL(string: "https://example.com/icon.png")) { image in
    image.resizable()
} placeholder: {
    ProgressView()
}
.frame(width: 50, height: 50)
```参数

在此示例中，SwiftUI 首先显示[ProgressView](ProgressView.zh-Hans.md)，然后显示按比例调整以适合指定帧的图像：





要对加载过程进行更多控制，可以使用[init(url:scale:transaction:content:)](AsyncImage/init_url_scale_transaction_content.zh-Hans.md) 初始化器，该初始化器接收`content` 闭包，并接收[AsyncImagePhase](AsyncImagePhase.zh-Hans.md) 以指示加载操作的状态。返回适合当前阶段的视图：

```swift
AsyncImage(url: URL(string: "https://example.com/icon.png")) { phase in
    if let image = phase.image {
        image // Displays the loaded image.
    } else if phase.error != nil {
        Color.red // Indicates an error.
    } else {
        Color.blue // Acts as a placeholder.
    }
}
```

## 正在加载图像

- **init(url:scale:)**：从指定的 URL 加载并显示图像。
- **init(url:scale:content:placeholder:)**：使用自定义占位符从指定的 URL 加载并显示可修改的图像，直到图像加载完毕。

## 分阶段加载图片

- **init(url:scale:transaction:content:)**：分阶段加载并显示指定 URL 中的可修改图片。

## 异步加载图像

- **AsyncImagePhase**：异步加载图像操作的当前阶段。

## 符合

- 查看


---
source: https://developer.apple.com/documentation/SwiftUI/AsyncImage
crawled: 2025-12-02T17:04:42Z
---

# AsyncImage

**Structure**

A view that asynchronously loads and displays an image.

## Declaration

```swift
struct AsyncImage<Content> where Content : View
```

## Overview

This view uses the shared [doc://com.apple.documentation/documentation/Foundation/URLSession] instance to load an image from the specified URL, and then display it. For example, you can display an icon that’s stored on a server:

```swift
AsyncImage(url: URL(string: "https://example.com/icon.png"))
    .frame(width: 200, height: 200)
```

Until the image loads, the view displays a standard placeholder that fills the available space. After the load completes successfully, the view updates to display the image. In the example above, the icon is smaller than the frame, and so appears smaller than the placeholder.



You can specify a custom placeholder using [init(url:scale:content:placeholder:)](AsyncImage/init_url_scale_content_placeholder.zh-Hans.md). With this initializer, you can also use the `content` parameter to manipulate the loaded image. For example, you can add a modifier to make the loaded image resizable:

```swift
AsyncImage(url: URL(string: "https://example.com/icon.png")) { image in
    image.resizable()
} placeholder: {
    ProgressView()
}
.frame(width: 50, height: 50)
```

For this example, SwiftUI shows a [ProgressView](ProgressView.zh-Hans.md) first, and then the image scaled to fit in the specified frame:





To gain more control over the loading process, use the [init(url:scale:transaction:content:)](AsyncImage/init_url_scale_transaction_content.zh-Hans.md) initializer, which takes a `content` closure that receives an [AsyncImagePhase](AsyncImagePhase.zh-Hans.md) to indicate the state of the loading operation. Return a view that’s appropriate for the current phase:

```swift
AsyncImage(url: URL(string: "https://example.com/icon.png")) { phase in
    if let image = phase.image {
        image // Displays the loaded image.
    } else if phase.error != nil {
        Color.red // Indicates an error.
    } else {
        Color.blue // Acts as a placeholder.
    }
}
```

## Loading an image

- **init(url:scale:)**: Loads and displays an image from the specified URL.
- **init(url:scale:content:placeholder:)**: Loads and displays a modifiable image from the specified URL using a custom placeholder until the image loads.

## Loading an image in phases

- **init(url:scale:transaction:content:)**: Loads and displays a modifiable image from the specified URL in phases.

## Loading images asynchronously

- **AsyncImagePhase**: The current phase of the asynchronous image loading operation.

## Conforms To

- View

