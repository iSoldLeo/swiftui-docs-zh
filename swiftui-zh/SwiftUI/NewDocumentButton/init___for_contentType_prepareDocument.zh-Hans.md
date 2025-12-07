---
来源：https://developer.apple.com/documentation/SwiftUI/NewDocumentButton/init(_:for:contentType:prepareDocument:)
抓取时间：2025-12-01T10:32:27Z


# init(_:for:contentType:prepareDocument:)

**Initializer**

创建并打开新文档。

## 声明

```swift
init<D>(_ label: Text? = nil, for documentType: D.Type = D.self, contentType: UTType? = nil, prepareDocument: @escaping () async throws -> D? = { nil }) where D : FileDocument
```

## 参数

- **label**：按钮的标签。
- **documentType**：要创建的文档类型。
- **contentType**：要创建的文档的可选内容类型。
- **prepareDocument**：要创建的文档类型：当用户按下按钮时会调用闭包。此时，您可以显示文档模板选择器或其他用户界面，让用户选择主题、配置或模板来创建文档。返回准备好的文档，如果文档创建失败，则抛出错误。返回 `nil` 以请求创建空文档。

## 讨论

一个显示文档模板选择器并创建文档的按钮可以这样实现：

```swift
   struct ChooseDocumentTemplateButton: View {
       @State private var showTemplatePicker = false
       @State private var documentCreationContinuation:
           CheckedContinuation<TextDocument?, any Error>?

       var body: some View {
           NewDocumentButton(for: TextDocument.self) {
               try await withCheckedThrowingContinuation { continuation in
                   documentCreationContinuation = continuation
                   showTemplatePicker = true
               }
           }
           .fullScreenCover(isPresented: $showTemplatePicker) {
               TemplatePicker($documentCreationContinuation)
           }
       }
   }

   struct TemplatePicker: View {
       @Binding var documentCreationContinuation:
           CheckedContinuation<TextDocument?, any Error>?

       ...

       func present(document: TextDocument) {
           documentCreationContinuation.resume(returning: document)
           documentCreationContinuation = nil
       }
   }

   struct TextDocument: FileDocument { ... }
```


---
source: https://developer.apple.com/documentation/SwiftUI/NewDocumentButton/init(_:for:contentType:prepareDocument:)
crawled: 2025-12-01T10:32:27Z
---

# init(_:for:contentType:prepareDocument:)

**Initializer**

Creates and opens new documents.

## Declaration

```swift
init<D>(_ label: Text? = nil, for documentType: D.Type = D.self, contentType: UTType? = nil, prepareDocument: @escaping () async throws -> D? = { nil }) where D : FileDocument
```

## Parameters

- **label**: A label for the button.
- **documentType**: A type of the document to create.
- **contentType**: An optional content type of the document to create.
- **prepareDocument**: A closure is called when a user presses the button. At this point, you can present a document template picker or another UI that allows users to choose a theme, configuration, or a template to create a document from. Return a prepared document, or throw an error if document creation failed. Return `nil` to request creation of an empty document.

## Discussion

A button that presents a document template picker and creates documents can be implemented like this:

```swift
   struct ChooseDocumentTemplateButton: View {
       @State private var showTemplatePicker = false
       @State private var documentCreationContinuation:
           CheckedContinuation<TextDocument?, any Error>?

       var body: some View {
           NewDocumentButton(for: TextDocument.self) {
               try await withCheckedThrowingContinuation { continuation in
                   documentCreationContinuation = continuation
                   showTemplatePicker = true
               }
           }
           .fullScreenCover(isPresented: $showTemplatePicker) {
               TemplatePicker($documentCreationContinuation)
           }
       }
   }

   struct TemplatePicker: View {
       @Binding var documentCreationContinuation:
           CheckedContinuation<TextDocument?, any Error>?

       ...

       func present(document: TextDocument) {
           documentCreationContinuation.resume(returning: document)
           documentCreationContinuation = nil
       }
   }

   struct TextDocument: FileDocument { ... }
```

