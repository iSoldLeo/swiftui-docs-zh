--- 来源：https://developer.apple.com/documentation/SwiftUI/View/onChange(of:initial:_:)-4psgg

抓取时间：2025-12-02T16:24:17Z

---

# onChange(of:initial:_:)

**实例方法**

为该视图添加一个修饰符，当指定值更改时触发一个操作。

## 声明

```swift
nonisolated func onChange<V>(of value: V, initial: Bool = false, _ action: @escaping (V, V) -> Void) -> some View where V : Equatable

```

## 参数

- **value**：用于确定是否运行闭包的值。

- **initial**：是否应在该视图首次显示时运行此操作。

- **action**：值更改时要运行的闭包。

## 返回值

当指定值更改时触发操作的视图。

## 讨论

您可以使用 `onChange` 来触发副作用，例如当值发生变化时，例如 `Environment` 键或 `Binding` 键发生变化。

系统可能会在主 Actor 上调用动作闭包，因此请避免在闭包中执行长时间运行的任务。如果需要执行此类任务，请分离一个异步后台任务。

当值发生变化时，将调用新版本的闭包，因此任何捕获的值都将从被观察值变为新值时开始更新。旧值和新值都会传递给闭包。在以下代码示例中，`PlayerView` 将旧值和新值都传递给了模型。

```swift
struct PlayerView: View {
    var episode: Episode
    @State private var playState: PlayState = .paused

    var body: some View {
        VStack {
            Text(episode.title)
            Text(episode.showTitle)
            PlayButton(playState: $playState)
        }
        .onChange(of: playState) { oldState, newState in
            model.playStateDidChange(from: oldState, to: newState)
        }
    }
}
```


---
source: https://developer.apple.com/documentation/SwiftUI/View/onChange(of:initial:_:)-4psgg
crawled: 2025-12-02T16:24:17Z
---

# onChange(of:initial:_:)

**Instance Method**

Adds a modifier for this view that fires an action when a specific value changes.

## Declaration

```swift
nonisolated func onChange<V>(of value: V, initial: Bool = false, _ action: @escaping (V, V) -> Void) -> some View where V : Equatable

```

## Parameters

- **value**: The value to check against when determining whether to run the closure.
- **initial**: Whether the action should be run when this view initially appears.
- **action**: A closure to run when the value changes.

## Return Value

A view that fires an action when the specified value changes.

## Discussion

You can use `onChange` to trigger a side effect as the result of a value changing, such as an `Environment` key or a `Binding`.

The system may call the action closure on the main actor, so avoid long-running tasks in the closure. If you need to perform such tasks, detach an asynchronous background task.

When the value changes, the new version of the closure will be called, so any captured values will have their values from the time that the observed value has its new value. The old and new observed values are passed into the closure. In the following code example, `PlayerView` passes both the old and new values to the model.

```swift
struct PlayerView: View {
    var episode: Episode
    @State private var playState: PlayState = .paused

    var body: some View {
        VStack {
            Text(episode.title)
            Text(episode.showTitle)
            PlayButton(playState: $playState)
        }
        .onChange(of: playState) { oldState, newState in
            model.playStateDidChange(from: oldState, to: newState)
        }
    }
}
```

