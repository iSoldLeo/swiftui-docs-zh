--- 来源：https://developer.apple.com/documentation/SwiftUI/Scene/onChange(of:initial:_:)

抓取时间：2025-12-03T05:31:02Z

---

# onChange(of:initial:_:)

**实例方法**

添加一个在给定值更改时要执行的操作。

## 声明

```swift
nonisolated func onChange<V>(of value: V, initial: Bool = false, _ action: @escaping () -> Void) -> some Scene where V : Equatable

```

## 参数

- **value**：用于确定是否运行闭包的值。该值必须符合 [doc://com.apple.documentation/documentation/Swift/Equatable] 协议。

- **initial**：是否应在场景首次出现时运行此操作。

- **action**：值更改时要运行的闭包。

## 返回值

一个场景，用于响应变化而触发动作。

## 说明

使用此修饰符可在值发生变化时触发副作用，例如与 [Environment](../Environment.zh-Hans.md) 键或 [Binding](../Binding.zh-Hans.md) 关联的值。例如，当您注意到某个场景切换到后台时，可以清除缓存：

```swift
struct MyScene: Scene {
    @Environment(\.locale) private var locale
    @StateObject private var cache = LocalizationDataCache()

    var body: some Scene {
        WindowGroup {
            MyRootView(cache: cache)
        }
        .onChange(of: locale) {
            cache.empty()
        }
    }
}
```

系统可能会在主 Actor 上调用动作闭包，因此请避免在闭包中执行长时间运行的任务。如果需要执行此类任务，请分离异步后台任务：

```swift
.onChange(of: locale) {
    Task.detached(priority: .background) {
        // ...
    }
}
```

当值发生变化时，将调用新版本的闭包，因此任何捕获的值都将从观察到的值变为新值时开始更新。

## 监听变化

- **handlesExternalEvents(matching:)**：指定 SwiftUI 会针对哪些外部事件打开已修改场景的新实例。


---
source: https://developer.apple.com/documentation/SwiftUI/Scene/onChange(of:initial:_:)
crawled: 2025-12-03T05:31:02Z
---

# onChange(of:initial:_:)

**Instance Method**

Adds an action to perform when the given value changes.

## Declaration

```swift
nonisolated func onChange<V>(of value: V, initial: Bool = false, _ action: @escaping () -> Void) -> some Scene where V : Equatable

```

## Parameters

- **value**: The value to check when determining whether to run the closure. The value must conform to the [doc://com.apple.documentation/documentation/Swift/Equatable] protocol.
- **initial**: Whether the action should be run when this scene initially appears.
- **action**: A closure to run when the value changes.

## Return Value

A scene that triggers an action in response to a change.

## Discussion

Use this modifier to trigger a side effect when a value changes, like the value associated with an [Environment](../Environment.zh-Hans.md) key or a [Binding](../Binding.zh-Hans.md). For example, you can clear a cache when you notice that a scene moves to the background:

```swift
struct MyScene: Scene {
    @Environment(\.locale) private var locale
    @StateObject private var cache = LocalizationDataCache()

    var body: some Scene {
        WindowGroup {
            MyRootView(cache: cache)
        }
        .onChange(of: locale) {
            cache.empty()
        }
    }
}
```

The system may call the action closure on the main actor, so avoid long-running tasks in the closure. If you need to perform such tasks, detach an asynchronous background task:

```swift
.onChange(of: locale) {
    Task.detached(priority: .background) {
        // ...
    }
}
```

When the value changes, the new version of the closure will be called, so any captured values will have their values from the time that the observed value has its new value.

## Watching for changes

- **handlesExternalEvents(matching:)**: Specifies the external events for which SwiftUI opens a new instance of the modified scene.

