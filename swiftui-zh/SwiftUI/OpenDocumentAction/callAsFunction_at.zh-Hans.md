--- 来源：https://developer.apple.com/documentation/SwiftUI/OpenDocumentAction/callAsFunction(at:)

抓取时间：2025-12-01T10:48:04Z

---

# callAsFunction(at:)

**实例方法**

打开指定文件 URL 的文档。

## 声明

```swift
@MainActor func callAsFunction(at url: URL) async throws
```

## 参数

- **url**：指向现有文档的文件 URL。

## 说明

请勿直接调用此方法。当您调用 [openDocument](../EnvironmentValues/openDocument.zh-Hans.md) 操作时，SwiftUI 会调用它：

```swift
do {
    try await openDocument(at: url)
} catch {
    // Handle error
}
```

有关 Swift 如何使用 `callAsFunction()` 方法简化调用点语法的详细信息，请参阅《Swift 程序设计语言》中的 [https://docs.swift.org/swift-book/ReferenceManual/Declarations.html#ID622]。


---
source: https://developer.apple.com/documentation/SwiftUI/OpenDocumentAction/callAsFunction(at:)
crawled: 2025-12-01T10:48:04Z
---

# callAsFunction(at:)

**Instance Method**

Opens the document at the specified file URL.

## Declaration

```swift
@MainActor func callAsFunction(at url: URL) async throws
```

## Parameters

- **url**: A file URL that points at an existing document.

## Discussion

Don’t call this method directly. SwiftUI calls it when you call the [openDocument](../EnvironmentValues/openDocument.zh-Hans.md) action:

```swift
do {
    try await openDocument(at: url)
} catch {
    // Handle error
}
```

For information about how Swift uses the `callAsFunction()` method to simplify call site syntax, see [https://docs.swift.org/swift-book/ReferenceManual/Declarations.html#ID622] in *The Swift Programming Language*.

