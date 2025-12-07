---
来源：https://developer.apple.com/documentation/SwiftUI/DocumentGroup/init(viewing:migrationPlan:viewer:)
抓取时间： 2025-12-01T00:42:55Z
---

# init(viewing:migrationPlan:viewer:)

**Initializer**

实例化文档组，用于查看迁移计划中最后一个`Schema`描述的文档。

## 声明

```swift
init(viewing contentType: UTType, migrationPlan: any SchemaMigrationPlan.Type, viewer: @escaping () -> Content)
```

## 参数

- **viewing**：文件的内容类型。它应符合 `UTType.package`。
- **migrationPlan**：说明迁移旧版本文档使其可以打开所需的步骤。计划中的最后一个`VersionedSchema` 被视为当前应用模式。
- **viewer**：所提供文档的查看用户界面。

## 查看由持久存储支持的文档

- **init(viewing:contentType:viewer:)**：实例化一个文档组，用于查看存储特定模型类型的文档。


---
source: https://developer.apple.com/documentation/SwiftUI/DocumentGroup/init(viewing:migrationPlan:viewer:)
crawled: 2025-12-01T00:42:55Z
---

# init(viewing:migrationPlan:viewer:)

**Initializer**

Instantiates a document group for viewing documents described by the last `Schema` in the migration plan.

## Declaration

```swift
init(viewing contentType: UTType, migrationPlan: any SchemaMigrationPlan.Type, viewer: @escaping () -> Content)
```

## Parameters

- **viewing**: The content type of the document. It should conform to `UTType.package`.
- **migrationPlan**: The description of steps required to migrate older document versions so that they can be opened. The last `VersionedSchema` in the plan is considered to be the current application schema.
- **viewer**: The viewing UI for the provided document.

## Viewing a document backed by a persistent store

- **init(viewing:contentType:viewer:)**: Instantiates a document group for viewing documents that store a specific model type.

