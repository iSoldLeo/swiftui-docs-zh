--- 来源：https://developer.apple.com/documentation/SwiftUI/Scene/modelContext(_:)

抓取时间：2025-12-03T05:31:06Z

---

# modelContext(_:)

**实例方法**

设置此场景环境中的模型上下文。

## 声明

```swift
@MainActor @preconcurrency func modelContext(_ modelContext: ModelContext) -> some Scene

```

## 参数

- **modelContext**：要在此场景环境中设置的模型上下文。

## 说明

在本例中，`RecipesApp` 设置了一个共享的模型上下文，供其所有窗口使用：

```swift
@Model class Recipe { ... }

@main
struct RecipesApp: App {
    var body: some Scene {
        WindowGroup {
            RecipesList()
        }
        .modelContext(myContext)
    }
}
```

环境的 [modelContext](../EnvironmentValues/modelContext.zh-Hans.md) 属性将被赋值为 `myContext`。此场景中所有隐式模型上下文操作（例如 `Query` 属性）都将使用环境的上下文。

## 配置数据模型

- **modelContainer(_:)**：设置此场景环境中的模型容器及其关联的模型上下文。

- **modelContainer(for:inMemory:isAutosaveEnabled:isUndoEnabled:onSetup:)**：设置此场景中用于存储所提供模型类型的模型容器（如有必要，将创建新容器），并为该容器设置此场景环境中的模型上下文。


---
source: https://developer.apple.com/documentation/SwiftUI/Scene/modelContext(_:)
crawled: 2025-12-03T05:31:06Z
---

# modelContext(_:)

**Instance Method**

Sets the model context in this scene’s environment.

## Declaration

```swift
@MainActor @preconcurrency func modelContext(_ modelContext: ModelContext) -> some Scene

```

## Parameters

- **modelContext**: The model context to set in this scene’s environment.

## Discussion

In this example, `RecipesApp` sets a shared model context to use for all of its windows:

```swift
@Model class Recipe { ... }

@main
struct RecipesApp: App {
    var body: some Scene {
        WindowGroup {
            RecipesList()
        }
        .modelContext(myContext)
    }
}
```

The environment’s [modelContext](../EnvironmentValues/modelContext.zh-Hans.md) property will be assigned a `myContext`. All implicit model context operations in this scene, such as `Query` properties, will use the environment’s context.

## Configuring a data model

- **modelContainer(_:)**: Sets the model container and associated model context in this scene’s environment.
- **modelContainer(for:inMemory:isAutosaveEnabled:isUndoEnabled:onSetup:)**: Sets the model container in this scene for storing the provided model type, creating a new container if necessary, and also sets a model context for that container in this scene’s environment.

