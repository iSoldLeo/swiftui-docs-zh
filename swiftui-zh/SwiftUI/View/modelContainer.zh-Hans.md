--- 来源：https://developer.apple.com/documentation/SwiftUI/View/modelContainer(_:)

抓取时间：2025-12-01T10:24:23Z

---

# modelContainer(_:)

**实例方法**

设置此视图环境中的模型容器及其关联的模型上下文。

## 声明

```swift
@MainActor @preconcurrency func modelContainer(_ container: ModelContainer) -> some View

```

## 参数

- **container**：此视图要使用的模型容器。

## 说明

在本例中，`ContentView` 设置了要用于 `RecipesList` 的模型容器：

```swift
struct ContentView: View {
    @State private var container = ModelContainer(...)

    var body: some Scene {
        RecipesList()
            .modelContainer(container)
    }
}
```

环境的 [modelContext](../EnvironmentValues/modelContext.zh-Hans.md) 属性将被分配一个与此容器关联的新上下文。此视图中所有隐式模型上下文操作（例如 `Query` 属性）都将使用环境的上下文。

## 配置模型

- **modelContext(_:)**：设置此视图环境中的模型上下文。

- **modelContainer(for:inMemory:isAutosaveEnabled:isUndoEnabled:onSetup:)**：设置此视图中用于存储所提供模型类型的模型容器，必要时创建新容器，并为该容器在此视图环境中设置模型上下文。


---
source: https://developer.apple.com/documentation/SwiftUI/View/modelContainer(_:)
crawled: 2025-12-01T10:24:23Z
---

# modelContainer(_:)

**Instance Method**

Sets the model container and associated model context in this view’s environment.

## Declaration

```swift
@MainActor @preconcurrency func modelContainer(_ container: ModelContainer) -> some View

```

## Parameters

- **container**: The model container to use for this view.

## Discussion

In this example, `ContentView` sets a model container to use for `RecipesList`:

```swift
struct ContentView: View {
    @State private var container = ModelContainer(...)

    var body: some Scene {
        RecipesList()
            .modelContainer(container)
    }
}
```

The environment’s [modelContext](../EnvironmentValues/modelContext.zh-Hans.md) property will be assigned a new context associated with this container. All implicit model context operations in this view, such as `Query` properties, will use the environment’s context.

## Configuring a model

- **modelContext(_:)**: Sets the model context in this view’s environment.
- **modelContainer(for:inMemory:isAutosaveEnabled:isUndoEnabled:onSetup:)**: Sets the model container in this view for storing the provided model type, creating a new container if necessary, and also sets a model context for that container in this view’s environment.

