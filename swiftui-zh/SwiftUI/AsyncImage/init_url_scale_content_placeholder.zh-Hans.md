---
来源：https://developer.apple.com/documentation/SwiftUI/AsyncImage/init(url:scale:content:placeholder:)
抓取时间： 2025-12-01T09:42:57Z
---

# init(url:scale:content:placeholder:)

**Initializer**

使用自定义占位符从指定的 URL 加载并显示可修改的图片，直到图片加载完毕。

## 声明

```swift
init<I, P>(url: URL?, scale: CGFloat = 1, @ViewBuilder content: @escaping (Image) -> I, @ViewBuilder placeholder: @escaping () -> P) where Content == _ConditionalContent<I, P>, I : View, P : View
```

## 参数

- **url**：要显示的图像的 URL。
- **scale**：图像要使用的比例。默认值为 `1`。加载为高分辨率显示器设计的图像时，请设置不同的值。例如，为存储在磁盘文件中的图像设置`2` 后缀。
- **content**：一个闭包，将加载的图像作为输入，并返回要显示的视图。您可以直接返回图像，也可以在返回之前根据需要修改图像。
- **placeholder**：一个闭包，用于返回要显示的视图，直到加载操作成功完成。

## 讨论

在加载图像之前，SwiftUI 会显示您指定的占位符视图。加载操作成功完成后，SwiftUI 会更新视图以显示您指定的内容，这些内容是您使用加载的图像创建的。例如，您可以显示绿色占位符，然后显示已加载图像的平铺版本：

```swift
AsyncImage(url: URL(string: "https://example.com/icon.png")) { image in
    image.resizable(resizingMode: .tile)
} placeholder: {
    Color.green
}
```

如果加载操作失败，SwiftUI 将继续显示占位符。要在加载错误时显示不同的视图，请使用 [init(url:scale:transaction:content:)](init_url_scale_transaction_content.zh-Hans.md) 初始化器。

## 加载图像

- **init(url:scale:)**：从指定的 URL 加载并显示图像。


---
source: https://developer.apple.com/documentation/SwiftUI/AsyncImage/init(url:scale:content:placeholder:)
crawled: 2025-12-01T09:42:57Z
---

# init(url:scale:content:placeholder:)

**Initializer**

Loads and displays a modifiable image from the specified URL using a custom placeholder until the image loads.

## Declaration

```swift
init<I, P>(url: URL?, scale: CGFloat = 1, @ViewBuilder content: @escaping (Image) -> I, @ViewBuilder placeholder: @escaping () -> P) where Content == _ConditionalContent<I, P>, I : View, P : View
```

## Parameters

- **url**: The URL of the image to display.
- **scale**: The scale to use for the image. The default is `1`. Set a different value when loading images designed for higher resolution displays. For example, set a value of `2` for an image that you would name with the `@2x` suffix if stored in a file on disk.
- **content**: A closure that takes the loaded image as an input, and returns the view to show. You can return the image directly, or modify it as needed before returning it.
- **placeholder**: A closure that returns the view to show until the load operation completes successfully.

## Discussion

Until the image loads, SwiftUI displays the placeholder view that you specify. When the load operation completes successfully, SwiftUI updates the view to show content that you specify, which you create using the loaded image. For example, you can show a green placeholder, followed by a tiled version of the loaded image:

```swift
AsyncImage(url: URL(string: "https://example.com/icon.png")) { image in
    image.resizable(resizingMode: .tile)
} placeholder: {
    Color.green
}
```

If the load operation fails, SwiftUI continues to display the placeholder. To be able to display a different view on a load error, use the [init(url:scale:transaction:content:)](init_url_scale_transaction_content.zh-Hans.md) initializer instead.

## Loading an image

- **init(url:scale:)**: Loads and displays an image from the specified URL.

