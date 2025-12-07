---
来源： https://developer.apple.com/documentation/SwiftUI/AttributedTextFormatting/Transferable
抓取时间： 2025-12-03T06:18:47Z
---

# AttributedTextFormatting.Transferable

**Structure**

在 SwiftUI 环境中解释的属性字符串的可转移表示。

## 声明

```swift
struct Transferable
```

## 概览

使用这种类型，例如与拖放 API 配合使用，或创建[fileExporter(isPresented:item:contentTypes:defaultFilename:onCompletion:onCancellation:)](../View/fileExporter_isPresented_item_contentTypes_defaultFilename_onCompletion_onCancellation.zh-Hans.md)。

```swift
struct RichTextEditorView: View {
    @State private var text: AttributedString = ""
    @Environment(\.self) private var environment
    @State var fileExporterIsPresented: Bool = false

    var body: some View {
        TextEditor(text: $text)
            .toolbar {
                Button("Save") {
                    fileExporterIsPresented = true
                }
            }
            .fileExporter(
                isPresented: $fileExporterIsPresented,
                item: AttributedTextFormatting.Transferable(text: text, in: environment)
            ) { result in
                handleResult(result)
            }
            .dropDestination(
                for: AttributedTextFormatting.Transferable.self
            ) { transferables, _ in
                text.replaceSelection(
                    &selection,
                    with: transferables.map {
                        AttributedString(transferable: $0, in: environment)
                    }.joined(separator: AttributedString("\n")))
                return true
            }
    }
}
```

要在导入后提取文本，请使用属性字符串的 `Foundation/AttributedString/init(transferable:in:)`。

支持的内容类型包括

- [doc://com.apple.documentation/documentation/UniformTypeIdentifiers/UTType-swift.struct/rtfd]
- [doc://com.apple.documentation/documentation/UniformTypeIdentifiers/UTType-swift.struct/rtf]

## 初始化程序

- **init(text:in:)**：创建在 SwiftUI 环境中解释的属性字符串的可转移表示。

## 符合

- 可发送
- 可发送元类型
- 可转移


---
source: https://developer.apple.com/documentation/SwiftUI/AttributedTextFormatting/Transferable
crawled: 2025-12-03T06:18:47Z
---

# AttributedTextFormatting.Transferable

**Structure**

A transferable representation of an attributed string interpreted in a SwiftUI environment.

## Declaration

```swift
struct Transferable
```

## Overview

Use this type e.g. with drag and drop APIs or to create a [fileExporter(isPresented:item:contentTypes:defaultFilename:onCompletion:onCancellation:)](../View/fileExporter_isPresented_item_contentTypes_defaultFilename_onCompletion_onCancellation.zh-Hans.md).

```swift
struct RichTextEditorView: View {
    @State private var text: AttributedString = ""
    @Environment(\.self) private var environment
    @State var fileExporterIsPresented: Bool = false

    var body: some View {
        TextEditor(text: $text)
            .toolbar {
                Button("Save") {
                    fileExporterIsPresented = true
                }
            }
            .fileExporter(
                isPresented: $fileExporterIsPresented,
                item: AttributedTextFormatting.Transferable(text: text, in: environment)
            ) { result in
                handleResult(result)
            }
            .dropDestination(
                for: AttributedTextFormatting.Transferable.self
            ) { transferables, _ in
                text.replaceSelection(
                    &selection,
                    with: transferables.map {
                        AttributedString(transferable: $0, in: environment)
                    }.joined(separator: AttributedString("\n")))
                return true
            }
    }
}
```

To extract text the text after importing, use attributed string’s `Foundation/AttributedString/init(transferable:in:)`.

Supported content types include:

- [doc://com.apple.documentation/documentation/UniformTypeIdentifiers/UTType-swift.struct/rtfd]
- [doc://com.apple.documentation/documentation/UniformTypeIdentifiers/UTType-swift.struct/rtf]

## Initializers

- **init(text:in:)**: Create a transferable representation of an attributed string as interpreted in a SwiftUI environment.

## Conforms To

- Sendable
- SendableMetatype
- Transferable

