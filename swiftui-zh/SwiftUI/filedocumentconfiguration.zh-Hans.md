---
来源： https://developer.apple.com/documentation/swiftui/filedocumentconfiguration
抓取时间： 2025-12-04T13:07:50Z
---

# 文件文档配置

**Structure**

打开的文件文档的属性。

## 声明

```swift
struct FileDocumentConfiguration<Document> where Document : FileDocument
```

## 概览

当您创建具有值文件类型的 [DocumentGroup](DocumentGroup.zh-Hans.md) 时，会收到此结构的一个实例。使用它可以在查看器或编辑器中访问文件。

## 获取和设置文档

- **document**：当前文档模型。
- **$document**: 当前文档模型。

## 获取文档属性

- **fileURL**：打开的文件文档的 URL。
- **isEditable**：布尔值，表示是否可以编辑文档。

## 在结构实例中存储文档数据

- **FileDocument**：用于将文档序列化到文件或从文件序列化到文档的类型。


---
source: https://developer.apple.com/documentation/swiftui/filedocumentconfiguration
crawled: 2025-12-04T13:07:50Z
---

# FileDocumentConfiguration

**Structure**

The properties of an open file document.

## Declaration

```swift
struct FileDocumentConfiguration<Document> where Document : FileDocument
```

## Overview

You receive an instance of this structure when you create a [DocumentGroup](DocumentGroup.zh-Hans.md) with a value file type. Use it to access the document in your viewer or editor.

## Getting and setting the document

- **document**: The current document model.
- **$document**

## Getting document properties

- **fileURL**: The URL of the open file document.
- **isEditable**: A Boolean that indicates whether you can edit the document.

## Storing document data in a structure instance

- **FileDocument**: A type that you use to serialize documents to and from file.

