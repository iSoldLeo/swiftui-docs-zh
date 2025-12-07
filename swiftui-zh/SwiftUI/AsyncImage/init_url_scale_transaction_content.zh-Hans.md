---
来源：https://developer.apple.com/documentation/SwiftUI/AsyncImage/init(url:scale:transaction:content:)
抓取时间：2025-12-01T09:42:58Z
---

# init(url:scale:transaction:content:)

**Initializer**

分阶段从指定的 URL 加载并显示可修改的图像。

## 声明

```swift
init(url: URL?, scale: CGFloat = 1, transaction: Transaction = Transaction(), @ViewBuilder content: @escaping (AsyncImagePhase) -> Content)
```

## 参数

- **url**：要显示的图像的 URL。
- **scale**：图像要使用的比例。默认值为 `1`。加载为高分辨率显示器设计的图像时，请设置不同的值。例如，为存储在磁盘文件中的图像设置`2` 后缀。
- **transaction**：相位发生变化时使用的事务。
- **content**：一个闭包，将加载阶段作为输入，并返回指定阶段要显示的视图。

## 讨论

如果将异步图像的 URL 设为`nil`，或将 URL 设为一个值后但在加载操作完成前，则阶段为[empty](../AsyncImagePhase/empty.zh-Hans.md)。操作完成后，阶段会变成 [failure(_:)](../AsyncImagePhase/failure.zh-Hans.md) 或 [success(_:)](../AsyncImagePhase/success.zh-Hans.md)。在第一种情况下，阶段的[error](../AsyncImagePhase/error.zh-Hans.md) 值表示故障原因。在第二种情况下，相位的 [image](../AsyncImagePhase/image.zh-Hans.md) 属性包含已加载的图像。使用相位来驱动`content` 闭包的输出，该闭包定义了视图的外观：

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

要在更改 URL 时添加转换，请在[AsyncImage](../AsyncImage.zh-Hans.md) 中应用标识符。


---
source: https://developer.apple.com/documentation/SwiftUI/AsyncImage/init(url:scale:transaction:content:)
crawled: 2025-12-01T09:42:58Z
---

# init(url:scale:transaction:content:)

**Initializer**

Loads and displays a modifiable image from the specified URL in phases.

## Declaration

```swift
init(url: URL?, scale: CGFloat = 1, transaction: Transaction = Transaction(), @ViewBuilder content: @escaping (AsyncImagePhase) -> Content)
```

## Parameters

- **url**: The URL of the image to display.
- **scale**: The scale to use for the image. The default is `1`. Set a different value when loading images designed for higher resolution displays. For example, set a value of `2` for an image that you would name with the `@2x` suffix if stored in a file on disk.
- **transaction**: The transaction to use when the phase changes.
- **content**: A closure that takes the load phase as an input, and returns the view to display for the specified phase.

## Discussion

If you set the asynchronous image’s URL to `nil`, or after you set the URL to a value but before the load operation completes, the phase is [empty](../AsyncImagePhase/empty.zh-Hans.md). After the operation completes, the phase becomes either [failure(_:)](../AsyncImagePhase/failure.zh-Hans.md) or [success(_:)](../AsyncImagePhase/success.zh-Hans.md). In the first case, the phase’s [error](../AsyncImagePhase/error.zh-Hans.md) value indicates the reason for failure. In the second case, the phase’s [image](../AsyncImagePhase/image.zh-Hans.md) property contains the loaded image. Use the phase to drive the output of the `content` closure, which defines the view’s appearance:

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

To add transitions when you change the URL, apply an identifier to the [AsyncImage](../AsyncImage.zh-Hans.md).

