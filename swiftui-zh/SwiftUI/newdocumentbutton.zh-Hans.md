---
来源： https://developer.apple.com/documentation/swiftui/newdocumentbutton
抓取时间：2025-12-02T17:29:00Z
---

# 新文档按钮

**Structure**

用于创建和打开新文档的按钮。

## 声明

```swift
struct NewDocumentButton<Label> where Label : View
```

## 概览

使用新文档按钮可让用户选择在应用程序中创建文档。在下面的示例中，有两个新文档按钮，都支持[Text](Text.zh-Hans.md) 标签。当用户点击或单击第一个按钮时，系统会在文档浏览器中当前打开的目录中创建一个新文档。第二个按钮是根据模板创建新文档。

```swift
@State private var isTemplatePickerPresented = false
@State private var documentCreationContinuation:
    CheckedContinuation<TextDocument?, any Error>?

var body: some Scene {
    DocumentGroupLaunchScene("My Documents") {
        NewDocumentButton("Start Writing…")
        NewDocumentButton("Choose a Template", for: MyDocument.self) {
            try await withCheckedThrowingContinuation { continuation in
                documentCreationContinuation = continuation
                isTemplatePickerPresented = true
            }
        }
        .fullScreenCover(isPresented: $isTemplatePickerPresented) {
            TemplatePicker(continuation: $documentCreationContinuation)
        }
    }
}
```

如果不提供自定义标签，系统会提供一个带有默认 "创建文档 "标签的按钮。

## 初始化程序

- **init(_:contentType:)**：创建和打开新文档。
- **init(_:contentType:prepareDocumentURL:)**：创建并打开新文档。
- **init(_:for:contentType:prepareDocument:)**： 创建并打开新文档：创建并打开新文档。

## 配置文件启动体验

- **DocumentGroupLaunchScene**：基于文档的应用程序的启动场景。
- **DocumentLaunchView**：在启动与文档相关的用户体验时呈现的视图。
- **DocumentLaunchGeometryProxy**：用于访问场景框架及其标题视图的代理。
- **DefaultDocumentGroupLaunchActions**：文档组启动场景和文档启动视图的默认操作。
- **DocumentBaseBox**：允许设置其文档底座的方框，调用者无需知道方框及其底座的确切类型。

## 符合

- 查看


---
source: https://developer.apple.com/documentation/swiftui/newdocumentbutton
crawled: 2025-12-02T17:29:00Z
---

# NewDocumentButton

**Structure**

A button that creates and opens new documents.

## Declaration

```swift
struct NewDocumentButton<Label> where Label : View
```

## Overview

Use a new document button to give people the option to create documents in your app. In the following example, there are two new document buttons, both support [Text](Text.zh-Hans.md) labels. When the user taps or clicks the first button, the system creates a new document in the directory currently open in the document browser. The second button creates a new document from a template.

```swift
@State private var isTemplatePickerPresented = false
@State private var documentCreationContinuation:
    CheckedContinuation<TextDocument?, any Error>?

var body: some Scene {
    DocumentGroupLaunchScene("My Documents") {
        NewDocumentButton("Start Writing…")
        NewDocumentButton("Choose a Template", for: MyDocument.self) {
            try await withCheckedThrowingContinuation { continuation in
                documentCreationContinuation = continuation
                isTemplatePickerPresented = true
            }
        }
        .fullScreenCover(isPresented: $isTemplatePickerPresented) {
            TemplatePicker(continuation: $documentCreationContinuation)
        }
    }
}
```

If you don’t provide a custom label, the system provides a button with the default “Create Document” label.

## Initializers

- **init(_:contentType:)**: Creates and opens new documents.
- **init(_:contentType:prepareDocumentURL:)**: Creates and opens new documents.
- **init(_:for:contentType:prepareDocument:)**: Creates and opens new documents.

## Configuring the document launch experience

- **DocumentGroupLaunchScene**: A launch scene for document-based applications.
- **DocumentLaunchView**: A view to present when launching document-related user experience.
- **DocumentLaunchGeometryProxy**: A proxy for access to the frame of the scene and its title view.
- **DefaultDocumentGroupLaunchActions**: The default actions for the document group launch scene and the document launch view.
- **DocumentBaseBox**: A Box that allows setting its Document base not requiring the caller to know the exact types of the box and its base.

## Conforms To

- View

