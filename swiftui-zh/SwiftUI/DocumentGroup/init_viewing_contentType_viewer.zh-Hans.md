---
来源：https://developer.apple.com/documentation/SwiftUI/DocumentGroup/init(viewing:contentType:viewer:)
抓取时间：2025-12-02T20:58:51Z
---

# init(viewing:contentType:viewer:)

**Initializer**

实例化一个文档组，用于查看存储特定模型类型的文档。

## 声明

```swift
init(viewing modelType: any PersistentModel.Type, contentType: UTType, viewer: @escaping () -> Content)
```

## 参数

- **modelType**：定义每个文档所用模式的模型类型。
- **contentType**：应用程序可查看的文档内容类型。它应符合 `UTType.package`。
- **viewer**：所提供文档的查看用户界面。

## 讨论

```swift
 @main
 struct Todo: App {
     var body: some Scene {
         DocumentGroup(viewing: TodoItem.self, contentType: .todoItem) {
             ContentView()
         }
     }
 }

 extension UTType {
     static var todoItem = UTType(exportedAs: "com.myApp.todoItem")
 }
```



## 查看由持久存储支持的文档

- **init(viewing:migrationPlan:viewer:)**：实例化一个文档组，用于查看迁移计划中最后一个`Schema`描述的文档。


---
source: https://developer.apple.com/documentation/SwiftUI/DocumentGroup/init(viewing:contentType:viewer:)
crawled: 2025-12-02T20:58:51Z
---

# init(viewing:contentType:viewer:)

**Initializer**

Instantiates a document group for viewing documents that store a specific model type.

## Declaration

```swift
init(viewing modelType: any PersistentModel.Type, contentType: UTType, viewer: @escaping () -> Content)
```

## Parameters

- **modelType**: The model type defining the schema used for each document.
- **contentType**: The content type of document your app can view. It should conform to `UTType.package`.
- **viewer**: The viewing UI for the provided document.

## Discussion

```swift
 @main
 struct Todo: App {
     var body: some Scene {
         DocumentGroup(viewing: TodoItem.self, contentType: .todoItem) {
             ContentView()
         }
     }
 }

 extension UTType {
     static var todoItem = UTType(exportedAs: "com.myApp.todoItem")
 }
```



## Viewing a document backed by a persistent store

- **init(viewing:migrationPlan:viewer:)**: Instantiates a document group for viewing documents described by the last `Schema` in the migration plan.

