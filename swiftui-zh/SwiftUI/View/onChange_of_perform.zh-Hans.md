--- 来源：https://developer.apple.com/documentation/SwiftUI/View/onChange(of:perform:)

抓取时间：2025-12-03T05:35:47Z

---

# onChange(of:perform:)

**实例方法**

添加一个在给定值更改时要执行的操作。

## 声明

```swift
nonisolated func onChange<V>(of value: V, perform action: @escaping (V) -> Void) -> some View where V : Equatable

```

## 说明

使用此修饰符可在值更改时触发副作用，例如与 [Environment](../Environment.zh-Hans.md) 或 [Binding](../Binding.zh-Hans.md) 关联的值。例如，当您注意到场景移至后台时，可以清除缓存：

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

系统可能会在主 Actor 上调用操作闭包，因此请避免在闭包中执行长时间运行的任务。如果需要执行此类任务，请分离异步后台任务：

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

## 输入和事件修饰符

- **onTapGesture(count:coordinateSpace:perform:)**：添加一个操作，当此视图识别到点击手势时执行，并为该操作提供交互位置。

- **onLongPressGesture(minimumDuration:maximumDistance:pressing:perform:)**：添加一个操作，当此视图识别到长按手势时执行。

- **onLongPressGesture(minimumDuration:pressing:perform:)**：添加一个操作，当此视图识别到长按手势时执行。

- **onPasteCommand(of:perform:)**：添加一个操作，响应系统的粘贴命令。

- **onPasteCommand(of:validator:perform:)**：添加一个操作，用于响应系统的粘贴命令，并验证粘贴的项目。

- **onDrop(of:delegate:)**：定义一个拖放操作的目标位置，该位置的大小和位置与当前视图相同，其行为由指定的委托控制。

- **onDrop(of:isTargeted:perform:)**：定义一个拖放操作的目标位置，该位置使用您指定的闭包处理拖放的内容。

- **focusable(_:onFocusChange:)**：指定视图是否可聚焦，如果可聚焦，则添加一个操作，当视图获得焦点时执行。

- **onContinuousHover(coordinateSpace:perform:)**：添加一个操作，当指针进入、移动到视图边界内以及离开视图边界时执行。


---
source: https://developer.apple.com/documentation/SwiftUI/View/onChange(of:perform:)
crawled: 2025-12-03T05:35:47Z
---

# onChange(of:perform:)

**Instance Method**

Adds an action to perform when the given value changes.

## Declaration

```swift
nonisolated func onChange<V>(of value: V, perform action: @escaping (V) -> Void) -> some View where V : Equatable

```

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

## Input and events modifiers

- **onTapGesture(count:coordinateSpace:perform:)**: Adds an action to perform when this view recognizes a tap gesture, and provides the action with the location of the interaction.
- **onLongPressGesture(minimumDuration:maximumDistance:pressing:perform:)**: Adds an action to perform when this view recognizes a long press gesture.
- **onLongPressGesture(minimumDuration:pressing:perform:)**: Adds an action to perform when this view recognizes a long press gesture.
- **onPasteCommand(of:perform:)**: Adds an action to perform in response to the system’s Paste command.
- **onPasteCommand(of:validator:perform:)**: Adds an action to perform in response to the system’s Paste command with items that you validate.
- **onDrop(of:delegate:)**: Defines the destination for a drag and drop operation with the same size and position as this view, with behavior controlled by the given delegate.
- **onDrop(of:isTargeted:perform:)**: Defines the destination of a drag-and-drop operation that handles the dropped content with a closure that you specify.
- **focusable(_:onFocusChange:)**: Specifies if the view is focusable and, if so, adds an action to perform when the view comes into focus.
- **onContinuousHover(coordinateSpace:perform:)**: Adds an action to perform when the pointer enters, moves within, and exits the view’s bounds.

