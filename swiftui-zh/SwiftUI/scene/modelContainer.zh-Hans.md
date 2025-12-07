--- 来源：https://developer.apple.com/documentation/SwiftUI/Scene/modelContainer(_:)

抓取时间：2025-12-01T10:20:12Z

---

# modelContainer(_:)

**实例方法**

设置此场景环境中的模型容器及其关联的模型上下文。

## 声明

```swift
@MainActor @preconcurrency func modelContainer(_ container: ModelContainer) -> some Scene

```

## 参数

- **container**：此场景要使用的模型容器。

## 说明

在本例中，`RecipesApp` 设置了一个共享模型容器，供其所有窗口使用：

```swift
@main
struct RecipesApp: App {
    @State private var container = ModelContainer(...)

    var body: some Scene {
        WindowGroup {
            RecipesList()
        }
        .modelContainer(container)
    }
}
```

环境的 [modelContext](../EnvironmentValues/modelContext.zh-Hans.md) 属性将被分配一个与此容器关联的新上下文。此场景中所有隐式模型上下文操作（例如 `Query` 属性）都将使用环境的上下文。

## 配置数据模型

- **modelContext(_:)**：设置此场景环境中的模型上下文。

- **modelContainer(for:inMemory:isAutosaveEnabled:isUndoEnabled:onSetup:)**：设置此场景中用于存储所提供模型类型的模型容器（如有必要，将创建新容器），并为该容器在此场景环境中设置模型上下文。


---
source: https://developer.apple.com/documentation/SwiftUI/Scene/modelContainer(_:)
crawled: 2025-12-01T10:20:12Z
---

# modelContainer(_:)

**Instance Method**

Sets the model container and associated model context in this scene’s environment.

## Declaration

```swift
@MainActor @preconcurrency func modelContainer(_ container: ModelContainer) -> some Scene

```

## Parameters

- **container**: The model container to use for this scene.

## Discussion

In this example, `RecipesApp` sets a shared model container to use for all of its windows:

```swift
@main
struct RecipesApp: App {
    @State private var container = ModelContainer(...)

    var body: some Scene {
        WindowGroup {
            RecipesList()
        }
        .modelContainer(container)
    }
}
```

The environment’s [modelContext](../EnvironmentValues/modelContext.zh-Hans.md) property will be assigned a new context associated with this container. All implicit model context operations in this scene, such as `Query` properties, will use the environment’s context.

## Configuring a data model

- **modelContext(_:)**: Sets the model context in this scene’s environment.
- **modelContainer(for:inMemory:isAutosaveEnabled:isUndoEnabled:onSetup:)**: Sets the model container in this scene for storing the provided model type, creating a new container if necessary, and also sets a model context for that container in this scene’s environment.

