---
来源： https://developer.apple.com/documentation/SwiftUI/NewDocumentAction/callAsFunction(contentType:)
抓取时间： 2025-12-03T05:59:05Z
---

# callAsFunction(contentType:)

**实例方法**

显示一个新的文档窗口。

## 声明

```swift
@MainActor @preconcurrency func callAsFunction(contentType: UTType)
```

## 参数

- **contentType**：文件的内容类型。

## 讨论

不要直接调用此方法。SwiftUI 会在您调用 [newDocument](../EnvironmentValues/newDocument.zh-Hans.md) 操作时调用该方法：

```swift
newDocument(contentType: .todoList)

 extension UTType {
     static let todoList = UTType(exportedAs: "com.myApp.todoList")
 }
```



有关 Swift 如何使用`callAsFunction()` 方法简化调用站点语法的信息，请参阅 *The Swift Programming Language* 中的 [https://docs.swift.org/swift-book/ReferenceManual/Declarations.html#ID622]。

## 调用操作

- **callAsFunction(_:)**：显示新文档窗口。
- **callAsFunction(contentType:prepareDocument:)**：显示带有预设内容的新文档窗口。


---
source: https://developer.apple.com/documentation/SwiftUI/NewDocumentAction/callAsFunction(contentType:)
crawled: 2025-12-03T05:59:05Z
---

# callAsFunction(contentType:)

**Instance Method**

Presents a new document window.

## Declaration

```swift
@MainActor @preconcurrency func callAsFunction(contentType: UTType)
```

## Parameters

- **contentType**: The content type of the document.

## Discussion

Don’t call this method directly. SwiftUI calls it when you call the [newDocument](../EnvironmentValues/newDocument.zh-Hans.md) action:

```swift
newDocument(contentType: .todoList)

 extension UTType {
     static let todoList = UTType(exportedAs: "com.myApp.todoList")
 }
```



For information about how Swift uses the `callAsFunction()` method to simplify call site syntax, see [https://docs.swift.org/swift-book/ReferenceManual/Declarations.html#ID622] in *The Swift Programming Language*.

## Calling the action

- **callAsFunction(_:)**: Presents a new document window.
- **callAsFunction(contentType:prepareDocument:)**: Presents a new document window with preset contents.

