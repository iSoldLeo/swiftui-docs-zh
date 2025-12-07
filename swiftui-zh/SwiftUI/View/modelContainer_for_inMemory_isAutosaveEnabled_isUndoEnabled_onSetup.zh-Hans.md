--- 来源：https://developer.apple.com/documentation/SwiftUI/View/modelContainer(for:inMemory:isAutosaveEnabled:isUndoEnabled:onSetup:)

抓取时间：2025-12-03T05:35:18Z

---

# modelContainer(for:inMemory:isAutosaveEnabled:isUndoEnabled:onSetup:)

**实例方法**

设置此视图中用于存储所提供模型类型的模型容器，必要时创建新容器，并在此视图环境中为该容器设置模型上下文。

## 声明

```swift
@MainActor @preconcurrency func modelContainer(for modelType: any PersistentModel.Type, inMemory: Bool = false, isAutosaveEnabled: Bool = true, isUndoEnabled: Bool = false, onSetup: @escaping (Result<ModelContainer, any Error>) -> Void = { _ in }) -> some View

```

## 参数

- **modelType**：定义用于创建模型容器的模式的模型类型。

- **inMemory**：容器是否应仅将数据存储在内存中。

- **isAutosaveEnabled**：如果启用了自动保存，则使用 `true`。

- **isUndoEnabled**：在环境中使用 `undoManager` 来管理模型容器的撤销操作。

- **onSetup**：容器创建成功或失败时将调用的回调函数。

## 讨论

在本例中，`RecipesList` 视图设置了一个模型容器，用于存储其所有内容，该容器配置为存储 `Recipe` 的实例：

```swift
@Model class Recipe { ... }
...
RecipesList()
    .modelContainer(for: Recipe.self)
```

环境的 [modelContext](../EnvironmentValues/modelContext.zh-Hans.md) 属性将被分配一个与此容器关联的新上下文。此视图中所有隐式模型上下文操作（例如 `Query` 属性）都将使用环境的上下文。

默认情况下，容器会将模型数据持久存储在磁盘上。要仅在应用程序进程的生命周期内将数据存储在内存中，请将 `true` 传递给 `inMemory:` 参数。

容器只会创建一次。视图首次创建后传递给 `modelType` 和 `inMemory` 参数的新值将被忽略。

## 配置模型

- **modelContext(_:)**：设置此视图环境中的模型上下文。

- **modelContainer(_:)**：设置此视图环境中的模型容器及其关联的模型上下文。


---
source: https://developer.apple.com/documentation/SwiftUI/View/modelContainer(for:inMemory:isAutosaveEnabled:isUndoEnabled:onSetup:)
crawled: 2025-12-03T05:35:18Z
---

# modelContainer(for:inMemory:isAutosaveEnabled:isUndoEnabled:onSetup:)

**Instance Method**

Sets the model container in this view for storing the provided model type, creating a new container if necessary, and also sets a model context for that container in this view’s environment.

## Declaration

```swift
@MainActor @preconcurrency func modelContainer(for modelType: any PersistentModel.Type, inMemory: Bool = false, isAutosaveEnabled: Bool = true, isUndoEnabled: Bool = false, onSetup: @escaping (Result<ModelContainer, any Error>) -> Void = { _ in }) -> some View

```

## Parameters

- **modelType**: The model type defining the schema used to create the model container.
- **inMemory**: Whether the container should store data only in memory.
- **isAutosaveEnabled**: `true` if autosave is enabled.
- **isUndoEnabled**: Use `undoManager` in the environment to manage undo operations for the model container.
- **onSetup**: A callback that will be invoked when the creation of the container has has succeeded or failed.

## Discussion

In this example, the `RecipesList` view sets a model container to use for all of its contents, configured to store instances of `Recipe`:

```swift
@Model class Recipe { ... }
...
RecipesList()
    .modelContainer(for: Recipe.self)
```

The environment’s [modelContext](../EnvironmentValues/modelContext.zh-Hans.md) property will be assigned a new context associated with this container. All implicit model context operations in this view, such as `Query` properties, will use the environment’s context.

By default, the container stores its model data persistently on disk. To only store data in memory for the lifetime of the app’s process, pass `true` to the `inMemory:` parameter.

The container will only be created once. New values that are passed to the `modelType` and `inMemory` parameters after the view is first created will be ignored.

## Configuring a model

- **modelContext(_:)**: Sets the model context in this view’s environment.
- **modelContainer(_:)**: Sets the model container and associated model context in this view’s environment.

