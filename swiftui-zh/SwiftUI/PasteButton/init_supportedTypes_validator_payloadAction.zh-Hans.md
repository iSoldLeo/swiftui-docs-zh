--- 来源：https://developer.apple.com/documentation/SwiftUI/PasteButton/init(supportedTypes:validator:payloadAction:)

抓取时间：2025-12-03T05:43:37Z

---

# init(supportedTypes:validator:payloadAction:)

**Initializer**

创建一个粘贴按钮，该按钮接受来自剪贴板的特定数据类型，并在将数据发送到您的应用之前对其进行自定义验证。

## 声明

```swift
@MainActor @preconcurrency init<Payload>(supportedTypes: [String], validator: @escaping ([NSItemProvider]) -> Payload?, payloadAction: @escaping (Payload) -> Void)
```

## 参数

- **supportedTypes**：按钮支持的确切统一类型标识符。如果剪贴板不包含任何受支持的类型，则按钮将被禁用。

- **validator**：一个处理程序，接收剪贴板中符合 `payloadAction` 规范的内容。加载并检查这些项目，以确定是否验证按钮。如果加载到有效项目，则从此闭包返回该项目。如果剪贴板不包含任何有效项目，则返回 `nil` 以使按钮失效。

- **payloadAction**：用户单击按钮时调用的处理程序。此闭包接收 `validator` 的预处理结果。

## 讨论

根据应用程序对其支持类型的偏好顺序设置 `supportedTypes` 的内容。“粘贴”按钮采用剪贴板源支持的首选类型，并将其传递给 `validator` 闭包。

## 已弃用的初始化器

- **init(supportedTypes:payloadAction:)**：创建一个“粘贴”按钮，该按钮接受来自剪贴板的特定类型的数据。

- **init(supportedContentTypes:validator:payloadAction:)**：创建一个“粘贴”按钮，该按钮接受来自剪贴板的特定类型的数据，并在将数据发送到您的应用程序之前对其进行自定义验证。


---
source: https://developer.apple.com/documentation/SwiftUI/PasteButton/init(supportedTypes:validator:payloadAction:)
crawled: 2025-12-03T05:43:37Z
---

# init(supportedTypes:validator:payloadAction:)

**Initializer**

Creates a Paste button that accepts specific types of data from the pasteboard, performing a custom validation of the data before sending it to your app.

## Declaration

```swift
@MainActor @preconcurrency init<Payload>(supportedTypes: [String], validator: @escaping ([NSItemProvider]) -> Payload?, payloadAction: @escaping (Payload) -> Void)
```

## Parameters

- **supportedTypes**: The exact uniform type identifiers supported by the button. If the pasteboard doesn’t contain any of the supported types, the button becomes disabled.
- **validator**: A handler that receives those contents of the pasteboard that conform to `payloadAction`. Load and inspect these items to determine whether to validate the button. If you load a valid item, return it from this closure. If the pasteboard doesn’t contain any valid items, return `nil` to invalidate the button.
- **payloadAction**: The handler called when the user clicks the button. This closure receives the preprocessed result of `validator`.

## Discussion

Set the contents of `supportedTypes` in order of your app’s preference for its supported types. The Paste button takes the most-preferred type that the pasteboard source supports and delivers this to the `validator` closure.

## Deprecated initializers

- **init(supportedTypes:payloadAction:)**: Creates a Paste button that accepts specific types of data from the pasteboard.
- **init(supportedContentTypes:validator:payloadAction:)**: Creates a Paste button that accepts specific types of data from the pasteboard, performing a custom validation of the data before sending it to your app.

