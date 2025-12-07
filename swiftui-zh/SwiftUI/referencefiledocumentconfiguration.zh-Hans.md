--- 来源：https://developer.apple.com/documentation/swiftui/referencefiledocumentconfiguration
抓取时间：2025-12-04T13:07:53Z

---

# ReferenceFileDocumentConfiguration

**Structure**

已打开的参考文件文档的属性。

## 声明

```swift
@MainActor @preconcurrency struct ReferenceFileDocumentConfiguration<Document> where Document : ReferenceFileDocument
```

## 概述

当您创建参考文件类型的 [DocumentGroup](DocumentGroup.zh-Hans.md) 时，您将收到此结构的实例。您可以使用它在查看器或编辑器中访问该文档。

## 获取和设置文档

- **document**：当前文档模型。

- **$document**

## 获取文档属性

- **fileURL**：已打开的文件文档的 URL。

- **isEditable**：一个布尔值，指示是否可以编辑文档。

## 将文档数据存储在类实例中

- **ReferenceFileDocument**：用于将引用类型文档序列化为文件或从文件序列化文档的类型。

- **undoManager**：用于注册视图撤销操作的撤销管理器。


---
source: https://developer.apple.com/documentation/swiftui/referencefiledocumentconfiguration
crawled: 2025-12-04T13:07:53Z
---

# ReferenceFileDocumentConfiguration

**Structure**

The properties of an open reference file document.

## Declaration

```swift
@MainActor @preconcurrency struct ReferenceFileDocumentConfiguration<Document> where Document : ReferenceFileDocument
```

## Overview

You receive an instance of this structure when you create a [DocumentGroup](DocumentGroup.zh-Hans.md) with a reference file type. Use it to access the document in your viewer or editor.

## Getting and setting the document

- **document**: The current document model.
- **$document**

## Getting document properties

- **fileURL**: The URL of the open file document.
- **isEditable**: A Boolean that indicates whether you can edit the document.

## Storing document data in a class instance

- **ReferenceFileDocument**: A type that you use to serialize reference type documents to and from file.
- **undoManager**: The undo manager used to register a view’s undo operations.

