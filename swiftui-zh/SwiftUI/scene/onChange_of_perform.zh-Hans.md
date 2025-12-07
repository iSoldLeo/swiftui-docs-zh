--- 来源：https://developer.apple.com/documentation/SwiftUI/Scene/onChange(of:perform:)

抓取时间：2025-12-01T10:20:14Z

---

# onChange(of:perform:)

**实例方法**

添加一个在给定值更改时要执行的操作。

## 声明

```swift
nonisolated func onChange<V>(of value: V, perform action: @escaping (V) -> Void) -> some Scene where V : Equatable

```

## 参数

- **value**：用于确定是否运行闭包的值。该值必须符合 [doc://com.apple.documentation/documentation/Swift/Equatable] 协议。

- **action**：值更改时要运行的闭包。该闭包提供一个 `newValue` 参数，用于指示更改后的值。

## 返回值

一个响应更改而触发操作的场景。

## 讨论

使用此修饰符可在值发生变化时触发副作用，例如与 [Environment](../Environment.zh-Hans.md) 或 [Binding](../Binding.zh-Hans.md) 关联的值。例如，当您注意到场景切换到后台时，可以清除缓存：

```swift
struct MyScene: Scene {
    @Environment(\.scenePhase) private var scenePhase
    @StateObject private var cache = DataCache()

    var body: some Scene {
        WindowGroup {
            MyRootView()
        }
        .onChange(of: scenePhase) { newScenePhase in
            if newScenePhase == .background {
                cache.empty()
            }
        }
    }
}
```

系统可能会在主 Actor 上调用动作闭包，因此请避免在闭包中执行长时间运行的任务。如果需要执行此类任务，请分离异步后台任务：

```swift
.onChange(of: scenePhase) { newScenePhase in
    if newScenePhase == .background {
        Task.detached(priority: .background) {
            // ...
        }
    }
}
```

系统会将新值传递给闭包。如果需要旧值，请在闭包中捕获它。


---
source: https://developer.apple.com/documentation/SwiftUI/Scene/onChange(of:perform:)
crawled: 2025-12-01T10:20:14Z
---

# onChange(of:perform:)

**Instance Method**

Adds an action to perform when the given value changes.

## Declaration

```swift
nonisolated func onChange<V>(of value: V, perform action: @escaping (V) -> Void) -> some Scene where V : Equatable

```

## Parameters

- **value**: The value to check when determining whether to run the closure. The value must conform to the [doc://com.apple.documentation/documentation/Swift/Equatable] protocol.
- **action**: A closure to run when the value changes. The closure provides a single `newValue` parameter that indicates the changed value.

## Return Value

A scene that triggers an action in response to a change.

## Discussion

Use this modifier to trigger a side effect when a value changes, like the value associated with an [Environment](../Environment.zh-Hans.md) value or a [Binding](../Binding.zh-Hans.md). For example, you can clear a cache when you notice that a scene moves to the background:

```swift
struct MyScene: Scene {
    @Environment(\.scenePhase) private var scenePhase
    @StateObject private var cache = DataCache()

    var body: some Scene {
        WindowGroup {
            MyRootView()
        }
        .onChange(of: scenePhase) { newScenePhase in
            if newScenePhase == .background {
                cache.empty()
            }
        }
    }
}
```

The system may call the action closure on the main actor, so avoid long-running tasks in the closure. If you need to perform such tasks, detach an asynchronous background task:

```swift
.onChange(of: scenePhase) { newScenePhase in
    if newScenePhase == .background {
        Task.detached(priority: .background) {
            // ...
        }
    }
}
```

The system passes the new value into the closure. If you need the old value, capture it in the closure.

