--- 来源：https://developer.apple.com/documentation/SwiftUI/Scene/immersiveEnvironmentBehavior(_:)

抓取时间：2025-12-01T10:20:15Z

---

# immersiveEnvironmentBehavior(_:)

**实例方法**

设置此场景打开时应应用的沉浸式环境行为。

## 声明

```swift
nonisolated func immersiveEnvironmentBehavior(_ behavior: ImmersiveEnvironmentBehavior) -> some Scene

```

## 参数

- **behavior**：此场景打开时系统应应用的沉浸式环境行为。

## 返回值

使用指定 `behavior` 的场景。

## 讨论

使用此修饰符可以控制当打开 [ImmersiveSpace](../ImmersiveSpace.zh-Hans.md) 时沉浸式环境的行为，该 [ImmersiveSpace](../ImmersiveSpace.zh-Hans.md) 使用支持保持沉浸式环境可见的沉浸式样式。

例如，以下应用程序定义了一个显示交互式汽车发动机模型的沉浸式空间，通过将系统环境行为设置为 `.coexist`，可以在查看发动机细节时保持沉浸式环境的显示：

```swift
@main
struct App: App {
    var body: some Scene {
        ImmersiveSpace {
            CarEngineModel()
        }
        .immersiveEnvironmentBehavior(.coexist)
    }
}
```

注意：此行为是一种偏好设置，系统并非总是必须遵循。


---
source: https://developer.apple.com/documentation/SwiftUI/Scene/immersiveEnvironmentBehavior(_:)
crawled: 2025-12-01T10:20:15Z
---

# immersiveEnvironmentBehavior(_:)

**Instance Method**

Sets the immersive environment behavior that should apply when this scene opens.

## Declaration

```swift
nonisolated func immersiveEnvironmentBehavior(_ behavior: ImmersiveEnvironmentBehavior) -> some Scene

```

## Parameters

- **behavior**: A immersive environment behavior that should be applied by the system when this scene opens.

## Return Value

A scene that uses the specified `behavior`.

## Discussion

Use this modifier to control how the immersive environment behaves when an [ImmersiveSpace](../ImmersiveSpace.zh-Hans.md) is opened, that uses an immersion style that supports keeping the immersive environment visible.

For example, the following app defines an Immersive Space that displays an interactive car engine model, and by setting the system environment behavior to `.coexist`, the immersive environment can remain shown while inspecting the details of the engine:

```swift
@main
struct App: App {
    var body: some Scene {
        ImmersiveSpace {
            CarEngineModel()
        }
        .immersiveEnvironmentBehavior(.coexist)
    }
}
```

Note: The behavior is a preference and does not always have to be honored by the system.

