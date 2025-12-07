---
来源： https://developer.apple.com/documentation/SwiftUI/OpenDocumentAction
抓取时间： 2025-12-02T17:29:24Z
---

# OpenDocumentAction

**Structure**

显示现有文档的操作。

## 声明

```swift
@MainActor struct OpenDocumentAction
```

## 概览

使用[openDocument](EnvironmentValues/openDocument.zh-Hans.md) 环境值获取给定[Environment](Environment.zh-Hans.md) 的该结构的实例。然后调用该实例来显示现有文档。直接调用实例是因为它定义了一个 [callAsFunction(at:)](OpenDocumentAction/callAsFunction_at.zh-Hans.md) 方法，Swift 在调用实例时会调用该方法。

例如，您可以创建一个按钮，打开指定 URL 上的文档：

```swift
struct OpenDocumentButton: View {
    var url: URL
    @Environment(\.openDocument) private var openDocument

    var body: some View {
        Button(url.deletingPathExtension().lastPathComponent) {
            Task {
                do {
                    try await openDocument(at: url)
                } catch {
                    // Handle error
                }
            }
        }
    }
}
```

上面的示例使用`do-catch` 语句来处理打开文档操作可能产生的任何错误。由于该操作是异步操作，因此它还将该操作置于任务中并等待结果。

要显示现有文档，您的应用程序必须定义一个[DocumentGroup](DocumentGroup.zh-Hans.md) 来处理指定文件的内容类型。对于已打开的文件，系统会将现有窗口置于最前面。否则，系统会打开一个新窗口。

## 调用操作

- **callAsFunction(at:)**：在指定的文件 URL 上打开文档。

## 以编程方式打开文档

- **newDocument**：环境中显示新文档的操作。
- **NewDocumentAction**：显示新文档的操作。
- **openDocument**：环境中显示现有文档的操作。

## 符合

- 可发送
- 可发送元类型


---
source: https://developer.apple.com/documentation/SwiftUI/OpenDocumentAction
crawled: 2025-12-02T17:29:24Z
---

# OpenDocumentAction

**Structure**

An action that presents an existing document.

## Declaration

```swift
@MainActor struct OpenDocumentAction
```

## Overview

Use the [openDocument](EnvironmentValues/openDocument.zh-Hans.md) environment value to get the instance of this structure for a given [Environment](Environment.zh-Hans.md). Then call the instance to present an existing document. You call the instance directly because it defines a [callAsFunction(at:)](OpenDocumentAction/callAsFunction_at.zh-Hans.md) method that Swift calls when you call the instance.

For example, you can create a button that opens the document at the specified URL:

```swift
struct OpenDocumentButton: View {
    var url: URL
    @Environment(\.openDocument) private var openDocument

    var body: some View {
        Button(url.deletingPathExtension().lastPathComponent) {
            Task {
                do {
                    try await openDocument(at: url)
                } catch {
                    // Handle error
                }
            }
        }
    }
}
```

The above example uses a `do-catch` statement to handle any errors that the open document action might throw. It also places the action inside a task and awaits the result because the action operates asynchronously.

To present an existing document, your app must define a [DocumentGroup](DocumentGroup.zh-Hans.md) that handles the content type of the specified file. For a document that’s already open, the system brings the existing window to the front. Otherwise, the system opens a new window.

## Calling the action

- **callAsFunction(at:)**: Opens the document at the specified file URL.

## Opening a document programmatically

- **newDocument**: An action in the environment that presents a new document.
- **NewDocumentAction**: An action that presents a new document.
- **openDocument**: An action in the environment that presents an existing document.

## Conforms To

- Sendable
- SendableMetatype

