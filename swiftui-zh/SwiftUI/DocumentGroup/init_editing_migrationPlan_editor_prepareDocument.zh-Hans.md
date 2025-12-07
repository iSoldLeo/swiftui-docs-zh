---
来源：https://developer.apple.com/documentation/SwiftUI/DocumentGroup/init(editing:migrationPlan:editor:prepareDocument:)
抓取时间：2025-12-02T20:58:50Z


# init(editing:migrationPlan:editor:prepareDocument:)

**Initializer**

实例化文档组，用于创建和编辑迁移计划中最后一个`Schema`描述的文档。

## 声明

```swift
init(editing contentType: UTType, migrationPlan: any SchemaMigrationPlan.Type, editor: @escaping () -> Content, prepareDocument: @escaping (ModelContext) -> Void = { _ in })
```

## 参数

- **editing**：文件的内容类型。它应符合 `UTType.package`。
- **migrationPlan**：说明迁移旧版本文档使其可以打开和编辑所需的步骤。计划中的最后一个`VersionedSchema` 被视为当前应用模式。
- **editor**：所提供文档的编辑用户界面。

## 编辑由持久性存储支持的文档

- **init(editing:contentType:editor:prepareDocument:)**：实例化一个文档组，用于创建和编辑存储特定模型类型的文档。


---
source: https://developer.apple.com/documentation/SwiftUI/DocumentGroup/init(editing:migrationPlan:editor:prepareDocument:)
crawled: 2025-12-02T20:58:50Z
---

# init(editing:migrationPlan:editor:prepareDocument:)

**Initializer**

Instantiates a document group for creating and editing documents described by the last `Schema` in the migration plan.

## Declaration

```swift
init(editing contentType: UTType, migrationPlan: any SchemaMigrationPlan.Type, editor: @escaping () -> Content, prepareDocument: @escaping (ModelContext) -> Void = { _ in })
```

## Parameters

- **editing**: The content type of the document. It should conform to `UTType.package`.
- **migrationPlan**: The description of steps required to migrate older document versions so that they can be opened and edited. The last `VersionedSchema` in the plan is considered to be the current application schema.
- **editor**: The editing UI for the provided document.

## Editing a document backed by a persistent store

- **init(editing:contentType:editor:prepareDocument:)**: Instantiates a document group for creating and editing documents that store a specific model type.

