---
来源： https://developer.apple.com/documentation/SwiftUI/NewDocumentAction
抓取时间： 2025-12-02T17:29:23Z
---

# NewDocumentAction

**Structure**

显示新文档的操作。

## 声明

```swift
@MainActor @preconcurrency struct NewDocumentAction
```

## 概览

使用[newDocument](EnvironmentValues/newDocument.zh-Hans.md) 环境值为给定的[Environment](Environment.zh-Hans.md) 获取此结构的实例。然后调用该实例来显示新文档。直接调用实例是因为它定义了一个 [callAsFunction(_:)](NewDocumentAction/callAsFunction.zh-Hans.md) 方法，Swift 在调用实例时会调用该方法。

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

上例假定您定义了符合[FileDocument](FileDocument.zh-Hans.md) 或[ReferenceFileDocument](ReferenceFileDocument.zh-Hans.md) 协议的`TextDocument` 和处理相关文件类型的[DocumentGroup](DocumentGroup.zh-Hans.md)。

## 调用操作

- **callAsFunction(_:)**：显示一个新的文件窗口。
- **callAsFunction(contentType:)**：显示新文档窗口。
- **callAsFunction(contentType:prepareDocument:)**：显示带有预设内容的新文档窗口。

## 以编程方式打开文档

- **newDocument**：环境中显示新文档的操作。
- **openDocument**：环境中显示现有文档的操作。
- **OpenDocumentAction**：显示现有文档的操作。

## 符合

- 可发送
- 可发送元类型


---
source: https://developer.apple.com/documentation/SwiftUI/NewDocumentAction
crawled: 2025-12-02T17:29:23Z
---

# NewDocumentAction

**Structure**

An action that presents a new document.

## Declaration

```swift
@MainActor @preconcurrency struct NewDocumentAction
```

## Overview

Use the [newDocument](EnvironmentValues/newDocument.zh-Hans.md) environment value to get the instance of this structure for a given [Environment](Environment.zh-Hans.md). Then call the instance to present a new document. You call the instance directly because it defines a [callAsFunction(_:)](NewDocumentAction/callAsFunction.zh-Hans.md) method that Swift calls when you call the instance.

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

The above example assumes that you define a `TextDocument` that conforms to the [FileDocument](FileDocument.zh-Hans.md) or [ReferenceFileDocument](ReferenceFileDocument.zh-Hans.md) protocol, and a [DocumentGroup](DocumentGroup.zh-Hans.md) that handles the associated file type.

## Calling the action

- **callAsFunction(_:)**: Presents a new document window.
- **callAsFunction(contentType:)**: Presents a new document window.
- **callAsFunction(contentType:prepareDocument:)**: Presents a new document window with preset contents.

## Opening a document programmatically

- **newDocument**: An action in the environment that presents a new document.
- **openDocument**: An action in the environment that presents an existing document.
- **OpenDocumentAction**: An action that presents an existing document.

## Conforms To

- Sendable
- SendableMetatype

