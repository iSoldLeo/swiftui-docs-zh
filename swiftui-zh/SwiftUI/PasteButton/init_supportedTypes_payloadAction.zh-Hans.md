--- 来源：https://developer.apple.com/documentation/SwiftUI/PasteButton/init(supportedTypes:payloadAction:)

抓取时间：2025-12-01T10:32:48Z

---

# init(supportedTypes:payloadAction:)

**Initializer**

创建一个粘贴按钮，该按钮接受来自剪贴板的特定数据类型。

## 声明

```swift
@MainActor @preconcurrency init(supportedTypes: [String], payloadAction: @escaping ([NSItemProvider]) -> Void)
```

## 参数

- **supportedTypes**：按钮支持的确切统一类型标识符。如果剪贴板不包含任何受支持的类型，则按钮将被禁用。

- **payloadAction**：当用户单击粘贴按钮且剪贴板包含符合 `supportedTypes` 定义的项时要调用的处理程序。此闭包接收一个项目提供程序数组，您可以使用这些提供程序来检查和加载剪贴板数据。

## 讨论

根据应用程序对其支持类型的偏好顺序设置 `supportedTypes` 的内容。“粘贴”按钮会获取剪贴板源支持的首选类型，并将其传递给 `payloadAction` 闭包。

## 已弃用的初始化程序

- **init(supportedTypes:validator:payloadAction:)**：创建一个“粘贴”按钮，该按钮接受来自剪贴板的特定类型的数据，并在将数据发送到您的应用程序之前执行自定义验证。

- **init(supportedContentTypes:validator:payloadAction:)**：创建一个“粘贴”按钮，该按钮接受来自剪贴板的特定类型的数据，并在将数据发送到您的应用程序之前执行自定义验证。


---
source: https://developer.apple.com/documentation/SwiftUI/PasteButton/init(supportedTypes:payloadAction:)
crawled: 2025-12-01T10:32:48Z
---

# init(supportedTypes:payloadAction:)

**Initializer**

Creates a Paste button that accepts specific types of data from the pasteboard.

## Declaration

```swift
@MainActor @preconcurrency init(supportedTypes: [String], payloadAction: @escaping ([NSItemProvider]) -> Void)
```

## Parameters

- **supportedTypes**: The exact uniform type identifiers supported by the button. If the pasteboard doesn’t contain any of the supported types, the button becomes disabled.
- **payloadAction**: The handler to call when the user clicks the Paste button, and the pasteboard has items that conform to `supportedTypes`. This closure receives an array of item providers that you use to inspect and load the pasteboard data.

## Discussion

Set the contents of `supportedTypes` in order of your app’s preference for its supported types. The Paste button takes the most-preferred type that the pasteboard source supports and delivers this to the `payloadAction` closure.

## Deprecated initializers

- **init(supportedTypes:validator:payloadAction:)**: Creates a Paste button that accepts specific types of data from the pasteboard, performing a custom validation of the data before sending it to your app.
- **init(supportedContentTypes:validator:payloadAction:)**: Creates a Paste button that accepts specific types of data from the pasteboard, performing a custom validation of the data before sending it to your app.

