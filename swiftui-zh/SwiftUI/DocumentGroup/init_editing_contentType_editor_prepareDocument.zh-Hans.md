---
来源：https://developer.apple.com/documentation/SwiftUI/DocumentGroup/init(editing:contentType:editor:prepareDocument:)
抓取时间：2025-12-02T20:58:49Z


# init(editing:contentType:editor:prepareDocument:)

**Initializer**

实例化文档组，用于创建和编辑存储特定模型类型的文档。

## 声明

```swift
init(editing modelType: any PersistentModel.Type, contentType: UTType, editor: @escaping () -> Content, prepareDocument: @escaping (ModelContext) -> Void = { _ in })
```

## 参数

- **modelType**：定义每个文档所用模式的模型类型。
- **contentType**：文档的内容类型。它应符合 `UTType.package`。
- **editor**：所提供文档的编辑用户界面。
- **prepareDocument**：可选的闭包，用于接受与新文档关联的`ModelContext`。使用此闭包可以在文档显示前设置其初始内容：在提供的`ModelContext`中插入预配置的模型。

## 讨论

```swift
 @main
 struct Todo: App {
     var body: some Scene {
         DocumentGroup(editing: TodoItem.self, contentType: .todoItem) {
             ContentView()
         }
     }
 }

 struct ContentView: View {
     @Query var items: [TodoItem]

         var body: some View {
             List {
                 ForEach(items) { item in
                     @Bindable var item = item
                     Toggle(item.text, isOn: $item.isDone)
                 }
              }
         }
 }

 @Model
 final class TodoItem {
     var created: Date
     var text: String
     var isDone = false
 }

 extension UTType {
     static var todoItem = UTType(exportedAs: "com.myApp.todoItem")
 }
```



## 编辑由持久性存储支持的文档

- **init(editing:migrationPlan:editor:prepareDocument:)**：实例化一个文档组，用于创建和编辑迁移计划中最后一个`Schema`描述的文档。


---
source: https://developer.apple.com/documentation/SwiftUI/DocumentGroup/init(editing:contentType:editor:prepareDocument:)
crawled: 2025-12-02T20:58:49Z
---

# init(editing:contentType:editor:prepareDocument:)

**Initializer**

Instantiates a document group for creating and editing documents that store a specific model type.

## Declaration

```swift
init(editing modelType: any PersistentModel.Type, contentType: UTType, editor: @escaping () -> Content, prepareDocument: @escaping (ModelContext) -> Void = { _ in })
```

## Parameters

- **modelType**: The model type defining the schema used for each document.
- **contentType**: The content type of the document. It should conform to `UTType.package`.
- **editor**: The editing UI for the provided document.
- **prepareDocument**: The optional closure that accepts `ModelContext` associated with the new document. Use this closure to set the document’s initial contents before it is displayed: insert preconfigured models in the provided `ModelContext`.

## Discussion

```swift
 @main
 struct Todo: App {
     var body: some Scene {
         DocumentGroup(editing: TodoItem.self, contentType: .todoItem) {
             ContentView()
         }
     }
 }

 struct ContentView: View {
     @Query var items: [TodoItem]

         var body: some View {
             List {
                 ForEach(items) { item in
                     @Bindable var item = item
                     Toggle(item.text, isOn: $item.isDone)
                 }
              }
         }
 }

 @Model
 final class TodoItem {
     var created: Date
     var text: String
     var isDone = false
 }

 extension UTType {
     static var todoItem = UTType(exportedAs: "com.myApp.todoItem")
 }
```



## Editing a document backed by a persistent store

- **init(editing:migrationPlan:editor:prepareDocument:)**: Instantiates a document group for creating and editing documents described by the last `Schema` in the migration plan.

