---
来源：https://developer.apple.com/documentation/SwiftUI/NewDocumentAction/callAsFunction(contentType:prepareDocument:)
抓取时间： 2025-12-03T05:59:06Z
---

# callAsFunction(contentType:prepareDocument:)

**实例方法**

以预设内容显示新文档窗口。

## 声明

```swift
@MainActor @preconcurrency func callAsFunction(contentType: UTType, prepareDocument: @escaping (ModelContext) -> Void)
```

## 参数

- **contentType**：文件的内容类型。
- **prepareDocument**：接受与新文档相关联的`ModelContext` 的闭包。使用该闭包可以在文档显示前设置文档的初始内容：在提供的`ModelContext`中插入预配置的模型。

## 讨论

不要直接调用此方法。SwiftUI 会在您调用 [newDocument](../EnvironmentValues/newDocument.zh-Hans.md) 操作时调用它。

例如，Todo 应用程序可能会创建一个预填充 Todo 列表示例，作为入门体验的一部分：

```swift
newDocument(contentType: .todoList) { modelContext in
    let todoList = TodoList(
        title: "🎬 Movie night",
        items: [
            TodoItem(title: "🍿 Buy popcorn"),
            TodoItem(title: "🍨 Make some ice cream",
            TodoItem(title: "💡 Hang a string of lights")
        ]
    )
    modelContext.insert(todoList)
}
```

有关 Swift 如何使用`callAsFunction()` 方法简化调用站点语法的信息，请参阅 *The Swift Programming Language* 中的 [https://docs.swift.org/swift-book/ReferenceManual/Declarations.html#ID622]。

## 调用操作

- **callAsFunction(_:)**：显示新文档窗口。
- **callAsFunction(contentType:)**：显示新文档窗口。


---
source: https://developer.apple.com/documentation/SwiftUI/NewDocumentAction/callAsFunction(contentType:prepareDocument:)
crawled: 2025-12-03T05:59:06Z
---

# callAsFunction(contentType:prepareDocument:)

**Instance Method**

Presents a new document window with preset contents.

## Declaration

```swift
@MainActor @preconcurrency func callAsFunction(contentType: UTType, prepareDocument: @escaping (ModelContext) -> Void)
```

## Parameters

- **contentType**: The content type of the document.
- **prepareDocument**: The closure that accepts `ModelContext` associated with the new document. Use this closure to set the document’s initial contents before it is displayed: insert preconfigured models in the provided `ModelContext`.

## Discussion

Don’t call this method directly. SwiftUI calls it when you call the [newDocument](../EnvironmentValues/newDocument.zh-Hans.md) action.

For example, a Todo app might have a way to create a sample prepopulated Todo list as a part of onboarding experience:

```swift
newDocument(contentType: .todoList) { modelContext in
    let todoList = TodoList(
        title: "🎬 Movie night",
        items: [
            TodoItem(title: "🍿 Buy popcorn"),
            TodoItem(title: "🍨 Make some ice cream",
            TodoItem(title: "💡 Hang a string of lights")
        ]
    )
    modelContext.insert(todoList)
}
```

For information about how Swift uses the `callAsFunction()` method to simplify call site syntax, see [https://docs.swift.org/swift-book/ReferenceManual/Declarations.html#ID622] in *The Swift Programming Language*.

## Calling the action

- **callAsFunction(_:)**: Presents a new document window.
- **callAsFunction(contentType:)**: Presents a new document window.

