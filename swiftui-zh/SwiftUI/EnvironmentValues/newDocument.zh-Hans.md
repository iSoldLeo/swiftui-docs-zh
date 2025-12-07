---
来源： https://developer.apple.com/documentation/SwiftUI/EnvironmentValues/newDocument
抓取时间： 2025-12-02T17:29:22Z
---

# newDocument

**实例属性**

环境中显示新文档的操作。

## 声明

```swift
var newDocument: NewDocumentAction { get }
```

## 讨论

使用`newDocument` 环境值获取给定[NewDocumentAction](../NewDocumentAction.zh-Hans.md) 结构的[Environment](../Environment.zh-Hans.md) 实例。然后调用该实例来呈现新文档。我们直接调用实例是因为它定义了一个 [callAsFunction(_:)](../NewDocumentAction/callAsFunction.zh-Hans.md) 方法，当我们调用实例时，Swift 会调用该方法。

例如，您可以定义一个按钮，用选中的文本创建一个新文档：

```swift
struct NewDocumentFromSelection: View {
    @FocusedBinding(\.selectedText) private var selectedText: String?
    @Environment(\.newDocument) private var newDocument

    var body: some View {
        Button("New Document With Selection") {
            newDocument(TextDocument(text: selectedText))
        }
        .disabled(selectedText?.isEmpty != false)
    }
}
```

上例假定您定义了符合[FileDocument](../FileDocument.zh-Hans.md) 或[ReferenceFileDocument](../ReferenceFileDocument.zh-Hans.md) 协议的`TextDocument` 和处理相关文件类型的[DocumentGroup](../DocumentGroup.zh-Hans.md)。

## 以编程方式打开文档

- **NewDocumentAction**：显示新文档的操作。
- **openDocument**：环境中显示现有文档的操作。
- **OpenDocumentAction**：显示现有文档的操作。


---
source: https://developer.apple.com/documentation/SwiftUI/EnvironmentValues/newDocument
crawled: 2025-12-02T17:29:22Z
---

# newDocument

**Instance Property**

An action in the environment that presents a new document.

## Declaration

```swift
var newDocument: NewDocumentAction { get }
```

## Discussion

Use the `newDocument` environment value to get the instance of the [NewDocumentAction](../NewDocumentAction.zh-Hans.md) structure for a given [Environment](../Environment.zh-Hans.md). Then call the instance to present a new document. You call the instance directly because it defines a [callAsFunction(_:)](../NewDocumentAction/callAsFunction.zh-Hans.md) method that Swift calls when you call the instance.

For example, you can define a button that creates a new document from the selected text:

```swift
struct NewDocumentFromSelection: View {
    @FocusedBinding(\.selectedText) private var selectedText: String?
    @Environment(\.newDocument) private var newDocument

    var body: some View {
        Button("New Document With Selection") {
            newDocument(TextDocument(text: selectedText))
        }
        .disabled(selectedText?.isEmpty != false)
    }
}
```

The above example assumes that you define a `TextDocument` that conforms to the [FileDocument](../FileDocument.zh-Hans.md) or [ReferenceFileDocument](../ReferenceFileDocument.zh-Hans.md) protocol, and a [DocumentGroup](../DocumentGroup.zh-Hans.md) that handles the associated file type.

## Opening a document programmatically

- **NewDocumentAction**: An action that presents a new document.
- **openDocument**: An action in the environment that presents an existing document.
- **OpenDocumentAction**: An action that presents an existing document.

