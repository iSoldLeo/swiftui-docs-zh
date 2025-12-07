--- 来源：https://developer.apple.com/documentation/SwiftUI/PasteButton/init(payloadType:onPaste:)

抓取时间：2025-12-01T10:32:47Z

---

# init(payloadType:onPaste:)

**Initializer**

创建一个实例，该实例接受指定类型的值。

## 声明

```swift
@MainActor @preconcurrency init<T>(payloadType: T.Type, onPaste: @escaping ([T]) -> Void) where T : Transferable
```

## 参数

- **onPaste**：当剪贴板中至少有一个指定类型的项目时，要调用的按钮处理程序。

## 创建粘贴按钮

- **init(supportedContentTypes:payloadAction:)**：创建一个粘贴按钮，该按钮接受来自剪贴板的特定类型的数据。


---
source: https://developer.apple.com/documentation/SwiftUI/PasteButton/init(payloadType:onPaste:)
crawled: 2025-12-01T10:32:47Z
---

# init(payloadType:onPaste:)

**Initializer**

Creates an instance that accepts values of the specified type.

## Declaration

```swift
@MainActor @preconcurrency init<T>(payloadType: T.Type, onPaste: @escaping ([T]) -> Void) where T : Transferable
```

## Parameters

- **onPaste**: The handler to call on trigger of the button with at least one item of the specified `Transferable` type from the pasteboard.

## Creating a paste button

- **init(supportedContentTypes:payloadAction:)**: Creates a Paste button that accepts specific types of data from the pasteboard.

