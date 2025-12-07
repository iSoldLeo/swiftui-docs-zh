---
来源： https://developer.apple.com/documentation/SwiftUI/EnvironmentValues/undoManager
抓取时间： 2025-12-02T17:29:13Z
---

# undoManager

**实例属性**

用于注册视图撤销操作的撤销管理器。

## 声明

```swift
var undoManager: UndoManager? { get }
```

## 讨论

当环境表示不支持撤销和重做操作的上下文时，此值为`nil`。如果此值为`nil`，则可以跳过撤销操作的注册。

## 在类实例中存储文档数据

- **ReferenceFileDocument**：用于将引用类型文档序列化到文件或从文件序列化到引用类型文档的类型。
- **ReferenceFileDocumentConfiguration**：打开的引用文件文档的属性。


---
source: https://developer.apple.com/documentation/SwiftUI/EnvironmentValues/undoManager
crawled: 2025-12-02T17:29:13Z
---

# undoManager

**Instance Property**

The undo manager used to register a view’s undo operations.

## Declaration

```swift
var undoManager: UndoManager? { get }
```

## Discussion

This value is `nil` when the environment represents a context that doesn’t support undo and redo operations. You can skip registration of an undo operation when this value is `nil`.

## Storing document data in a class instance

- **ReferenceFileDocument**: A type that you use to serialize reference type documents to and from file.
- **ReferenceFileDocumentConfiguration**: The properties of an open reference file document.

