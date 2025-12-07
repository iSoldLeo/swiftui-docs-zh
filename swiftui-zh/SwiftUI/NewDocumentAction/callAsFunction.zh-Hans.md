---
来源： https://developer.apple.com/documentation/SwiftUI/NewDocumentAction/callAsFunction(_:)
抓取时间： 2025-12-03T05:59:04Z
---

# callAsFunction(_:)

**实例方法**

显示新的文档窗口。

## 声明

```swift
@MainActor @preconcurrency func callAsFunction<D>(_ newDocument: @autoclosure @escaping () -> D) where D : FileDocument
```

## 参数

- **newDocument**：要显示的新文件文档。

## 讨论

不要直接调用此方法。SwiftUI 会在您调用 [newDocument](../EnvironmentValues/newDocument.zh-Hans.md) 操作时调用它：

```swift
newDocument(TextDocument(text: selectedText))
```

有关 Swift 如何使用`callAsFunction()` 方法简化调用站点语法的信息，请参阅 *The Swift Programming Language* 中的 [https://docs.swift.org/swift-book/ReferenceManual/Declarations.html#ID622]。

## 调用操作

- **callAsFunction(contentType:)**：显示新文档窗口。
- **callAsFunction(contentType:prepareDocument:)**：显示带有预设内容的新文档窗口。


---
source: https://developer.apple.com/documentation/SwiftUI/NewDocumentAction/callAsFunction(_:)
crawled: 2025-12-03T05:59:04Z
---

# callAsFunction(_:)

**Instance Method**

Presents a new document window.

## Declaration

```swift
@MainActor @preconcurrency func callAsFunction<D>(_ newDocument: @autoclosure @escaping () -> D) where D : FileDocument
```

## Parameters

- **newDocument**: The new file document to present.

## Discussion

Don’t call this method directly. SwiftUI calls it when you call the [newDocument](../EnvironmentValues/newDocument.zh-Hans.md) action:

```swift
newDocument(TextDocument(text: selectedText))
```

For information about how Swift uses the `callAsFunction()` method to simplify call site syntax, see [https://docs.swift.org/swift-book/ReferenceManual/Declarations.html#ID622] in *The Swift Programming Language*.

## Calling the action

- **callAsFunction(contentType:)**: Presents a new document window.
- **callAsFunction(contentType:prepareDocument:)**: Presents a new document window with preset contents.

