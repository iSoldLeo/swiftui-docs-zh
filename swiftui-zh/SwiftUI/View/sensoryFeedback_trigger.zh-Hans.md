--- 来源：https://developer.apple.com/documentation/SwiftUI/View/sensoryFeedback(trigger:_:)

抓取时间：2025-11-30T21:21:16Z

---

# sensoryFeedback(trigger:_:)

**实例方法**

当提供的 `trigger` 值发生变化时，从 `feedback` 闭包返回时播放反馈。

## 声明

```swift
nonisolated func sensoryFeedback<T>(trigger: T, _ feedback: @escaping () -> SensoryFeedback?) -> some View where T : Equatable

```

## 参数

- **trigger**：用于监听变化以确定何时播放反馈的值。

- **feedback**：用于确定是否播放反馈以及在 `trigger` 变化时播放何种类型的反馈的闭包。

## 讨论

例如，您可以针对不同的状态转换播放不同的反馈：

```swift
struct MyView: View {
    @State private var isExpanded = false

    var body: some View {
        ContentView(isExpanded: $isExpanded)
            .sensoryFeedback(trigger: isExpanded) {
                isExpanded ? .impact : nil
            }
    }
}
```

当值发生变化时，将调用新版本的闭包，因此任何捕获的值都将从观察到的值变为新值时开始更新。

## 提供触觉反馈

- **sensoryFeedback(_:trigger:)**：当提供的 `trigger` 值发生变化时，播放指定的 `feedback`。

- **sensoryFeedback(_:trigger:condition:)**：当提供的 `trigger` 值发生变化且 `condition` 闭包返回 `true` 时，播放指定的 `feedback`。

- **SensoryFeedback**：代表一种可以播放的触觉和/或音频反馈类型。


---
source: https://developer.apple.com/documentation/SwiftUI/View/sensoryFeedback(trigger:_:)
crawled: 2025-11-30T21:21:16Z
---

# sensoryFeedback(trigger:_:)

**Instance Method**

Plays feedback when returned from the `feedback` closure after the provided `trigger` value changes.

## Declaration

```swift
nonisolated func sensoryFeedback<T>(trigger: T, _ feedback: @escaping () -> SensoryFeedback?) -> some View where T : Equatable

```

## Parameters

- **trigger**: A value to monitor for changes to determine when to play.
- **feedback**: A closure to determine whether to play the feedback and what type of feedback to play when `trigger` changes.

## Discussion

For example, you could play different feedback for different state transitions:

```swift
struct MyView: View {
    @State private var isExpanded = false

    var body: some View {
        ContentView(isExpanded: $isExpanded)
            .sensoryFeedback(trigger: isExpanded) {
                isExpanded ? .impact : nil
            }
    }
}
```

When the value changes, the new version of the closure will be called, so any captured values will have their values from the time that the observed value has its new value.

## Providing haptic feedback

- **sensoryFeedback(_:trigger:)**: Plays the specified `feedback` when the provided `trigger` value changes.
- **sensoryFeedback(_:trigger:condition:)**: Plays the specified `feedback` when the provided `trigger` value changes and the `condition` closure returns `true`.
- **SensoryFeedback**: Represents a type of haptic and/or audio feedback that can be played.

