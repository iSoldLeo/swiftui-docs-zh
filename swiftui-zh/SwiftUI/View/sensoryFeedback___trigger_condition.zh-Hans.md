--- 来源：https://developer.apple.com/documentation/SwiftUI/View/sensoryFeedback(_:trigger:condition:)

抓取时间：2025-11-30T21:21:17Z

---

# sensoryFeedback(_:trigger:condition:)

**实例方法**

当提供的 `trigger` 值发生变化且 `condition` 闭包返回 `true` 时，播放指定的 `feedback`。

## 声明

```swift
nonisolated func sensoryFeedback<T>(_ feedback: SensoryFeedback, trigger: T, condition: @escaping (T, T) -> Bool) -> some View where T : Equatable

```

## 参数

- **feedback**：要播放的反馈类型。

- **trigger**：要监视其变化以确定何时播放的值。

- **condition**：用于确定当 `trigger` 发生变化时是否播放反馈的闭包。

## 讨论

例如，您可以针对某些状态转换播放反馈：

```swift
struct MyView: View {
    @State private var phase = Phase.inactive

    var body: some View {
        ContentView(phase: $phase)
            .sensoryFeedback(.selection, trigger: phase) { old, new in
                old == .inactive || new == .expanded
            }
    }

    enum Phase {
        case inactive
        case preparing
        case active
        case expanded
    }
}
```

当值发生变化时，将调用闭包的新版本，因此任何捕获的值都将从观察到的值变为新值时开始更新。

## 提供触觉反馈

- **sensoryFeedback(_:trigger:)**：当提供的 `trigger` 值发生变化时，播放指定的 `feedback`。

- **sensoryFeedback(trigger:_:)**：当提供的 `trigger` 值发生变化后，从 `feedback` 闭包返回时，播放反馈。

- **SensoryFeedback**：代表一种可以播放的触觉和/或音频反馈类型。


---
source: https://developer.apple.com/documentation/SwiftUI/View/sensoryFeedback(_:trigger:condition:)
crawled: 2025-11-30T21:21:17Z
---

# sensoryFeedback(_:trigger:condition:)

**Instance Method**

Plays the specified `feedback` when the provided `trigger` value changes and the `condition` closure returns `true`.

## Declaration

```swift
nonisolated func sensoryFeedback<T>(_ feedback: SensoryFeedback, trigger: T, condition: @escaping (T, T) -> Bool) -> some View where T : Equatable

```

## Parameters

- **feedback**: Which type of feedback to play.
- **trigger**: A value to monitor for changes to determine when to play.
- **condition**: A closure to determine whether to play the feedback when `trigger` changes.

## Discussion

For example, you could play feedback for certain state transitions:

```swift
struct MyView: View {
    @State private var phase = Phase.inactive

    var body: some View {
        ContentView(phase: $phase)
            .sensoryFeedback(.selection, trigger: phase) { old, new in
                old == .inactive || new == .expanded
            }
    }

    enum Phase {
        case inactive
        case preparing
        case active
        case expanded
    }
}
```

When the value changes, the new version of the closure will be called, so any captured values will have their values from the time that the observed value has its new value.

## Providing haptic feedback

- **sensoryFeedback(_:trigger:)**: Plays the specified `feedback` when the provided `trigger` value changes.
- **sensoryFeedback(trigger:_:)**: Plays feedback when returned from the `feedback` closure after the provided `trigger` value changes.
- **SensoryFeedback**: Represents a type of haptic and/or audio feedback that can be played.

