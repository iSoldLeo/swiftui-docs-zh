---
来源：https://developer.apple.com/documentation/SwiftUI/AsyncImage/init(url:scale:)
抓取时间：2025-12-03T04:53:36Z
---

# init(url:scale:)

**Initializer**

从指定的 URL 加载并显示图像。

## 声明

```swift
init(url: URL?, scale: CGFloat = 1) where Content == Image
```

## 参数

- **url**：要显示的图像的 URL。
- **scale**：图像要使用的比例。默认值为 `1`。加载为高分辨率显示器设计的图像时，请设置不同的值。例如，为存储在磁盘文件中的图像设置`2` 值，该图像将以`@2x` 后缀命名。

## 讨论

在加载图像之前，SwiftUI 会显示默认占位符。加载操作成功完成后，SwiftUI 会更新视图以显示加载的图像。如果操作失败，SwiftUI 将继续显示占位符。下面的示例从示例服务器加载并显示一个图标：

```swift
AsyncImage(url: URL(string: "https://example.com/icon.png"))
```

如果要自定义占位符或应用特定于图像的修饰符（如 [resizable(capInsets:resizingMode:)](../Image/resizable_capInsets_resizingMode.zh-Hans.md) ）到加载的图像，请使用 [init(url:scale:content:placeholder:)](init_url_scale_content_placeholder.zh-Hans.md) 初始化器。

## 加载图像

- **init(url:scale:content:placeholder:)**：使用自定义占位符从指定的 URL 加载并显示可修改的图片，直到图片加载完毕。


---
source: https://developer.apple.com/documentation/SwiftUI/AsyncImage/init(url:scale:)
crawled: 2025-12-03T04:53:36Z
---

# init(url:scale:)

**Initializer**

Loads and displays an image from the specified URL.

## Declaration

```swift
init(url: URL?, scale: CGFloat = 1) where Content == Image
```

## Parameters

- **url**: The URL of the image to display.
- **scale**: The scale to use for the image. The default is `1`. Set a different value when loading images designed for higher resolution displays. For example, set a value of `2` for an image that you would name with the `@2x` suffix if stored in a file on disk.

## Discussion

Until the image loads, SwiftUI displays a default placeholder. When the load operation completes successfully, SwiftUI updates the view to show the loaded image. If the operation fails, SwiftUI continues to display the placeholder. The following example loads and displays an icon from an example server:

```swift
AsyncImage(url: URL(string: "https://example.com/icon.png"))
```

If you want to customize the placeholder or apply image-specific modifiers — like [resizable(capInsets:resizingMode:)](../Image/resizable_capInsets_resizingMode.zh-Hans.md) — to the loaded image, use the [init(url:scale:content:placeholder:)](init_url_scale_content_placeholder.zh-Hans.md) initializer instead.

## Loading an image

- **init(url:scale:content:placeholder:)**: Loads and displays a modifiable image from the specified URL using a custom placeholder until the image loads.

