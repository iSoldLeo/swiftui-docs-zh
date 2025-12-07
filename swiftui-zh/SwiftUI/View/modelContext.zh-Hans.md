--- 来源：https://developer.apple.com/documentation/SwiftUI/View/modelContext(_:)

抓取时间：2025-12-03T05:35:16Z

---

# modelContext(_:)

**实例方法**

设置此视图环境中的模型上下文。

## 声明

```swift
@MainActor @preconcurrency func modelContext(_ modelContext: ModelContext) -> some View

```

## 参数

- **modelContext**：要在此视图环境中设置的模型上下文。

## 说明

在本例中，`RecipesList` 视图设置了一个模型上下文，用于其所有内容：

```swift
@Model class Recipe { ... }
...
RecipesList()
    .modelContext(myContext)
```

环境的 [modelContext](../EnvironmentValues/modelContext.zh-Hans.md) 属性将被赋值为 `myContext`。此视图中所有隐式模型上下文操作（例如 `Query` 属性）都将使用环境的上下文。

## 配置模型

- **modelContainer(_:)**：设置此视图环境中的模型容器及其关联的模型上下文。

- **modelContainer(for:inMemory:isAutosaveEnabled:isUndoEnabled:onSetup:)**：设置此视图中用于存储所提供模型类型的模型容器，必要时创建新容器，并为该容器设置此视图环境中的模型上下文。


---
source: https://developer.apple.com/documentation/SwiftUI/View/modelContext(_:)
crawled: 2025-12-03T05:35:16Z
---

# modelContext(_:)

**Instance Method**

Sets the model context in this view’s environment.

## Declaration

```swift
@MainActor @preconcurrency func modelContext(_ modelContext: ModelContext) -> some View

```

## Parameters

- **modelContext**: The model context to set in this view’s environment.

## Discussion

In this example, the `RecipesList` view sets a model context to use for all of its content:

```swift
@Model class Recipe { ... }
...
RecipesList()
    .modelContext(myContext)
```

The environment’s [modelContext](../EnvironmentValues/modelContext.zh-Hans.md) property will be assigned `myContext`. All implicit model context operations in this view, such as `Query` properties, will use the environment’s context.

## Configuring a model

- **modelContainer(_:)**: Sets the model container and associated model context in this view’s environment.
- **modelContainer(for:inMemory:isAutosaveEnabled:isUndoEnabled:onSetup:)**: Sets the model container in this view for storing the provided model type, creating a new container if necessary, and also sets a model context for that container in this view’s environment.

