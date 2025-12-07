--- 来源：https://developer.apple.com/documentation/SwiftUI/PasteButton/init(supportedContentTypes:payloadAction:)

抓取时间：2025-12-03T05:43:35Z

---

# init(supportedContentTypes:payloadAction:)

**Initializer**

创建一个粘贴按钮，该按钮接受来自剪贴板的特定数据类型。

## 声明

```swift
@MainActor @preconcurrency init(supportedContentTypes: [UTType], payloadAction: @escaping ([NSItemProvider]) -> Void)
```

## 参数

- **supportedContentTypes**：按钮支持的确切统一类型标识符。如果剪贴板不包含任何受支持的类型，则按钮将被禁用。

- **payloadAction**：当用户点击“粘贴”按钮且剪贴板包含符合 `supportedContentTypes` 规范的项目时，要调用的处理程序。此闭包接收一个项目提供程序数组，您可以使用该数组来检查和加载剪贴板数据。

## 讨论

根据应用程序对其支持类型的偏好顺序设置 `supportedContentTypes` 的内容。“粘贴”按钮会获取剪贴板源支持的最优先类型，并将其传递给 `payloadAction` 闭包。

## 创建粘贴按钮

- **init(payloadType:onPaste:)**：创建一个接受指定类型值的实例。


---
source: https://developer.apple.com/documentation/SwiftUI/PasteButton/init(supportedContentTypes:payloadAction:)
crawled: 2025-12-03T05:43:35Z
---

# init(supportedContentTypes:payloadAction:)

**Initializer**

Creates a Paste button that accepts specific types of data from the pasteboard.

## Declaration

```swift
@MainActor @preconcurrency init(supportedContentTypes: [UTType], payloadAction: @escaping ([NSItemProvider]) -> Void)
```

## Parameters

- **supportedContentTypes**: The exact uniform type identifiers supported by the button. If the pasteboard doesn’t contain any of the supported types, the button becomes disabled.
- **payloadAction**: The handler to call when the user clicks the Paste button and the pasteboard has items that conform to `supportedContentTypes`. This closure receives an array of item providers that you use to inspect and load the pasteboard data.

## Discussion

Set the contents of `supportedContentTypes` in order of your app’s preference for its supported types. The Paste button takes the most-preferred type that the pasteboard source supports and delivers this to the `payloadAction` closure.

## Creating a paste button

- **init(payloadType:onPaste:)**: Creates an instance that accepts values of the specified type.

