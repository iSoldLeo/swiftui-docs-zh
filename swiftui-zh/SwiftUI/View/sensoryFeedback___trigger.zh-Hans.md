--- 来源：https://developer.apple.com/documentation/SwiftUI/View/sensoryFeedback(_:trigger:)

抓取时间：2025-12-02T17:36:09Z

---

# sensoryFeedback(_:trigger:)

**实例方法**

当提供的 `trigger` 值发生变化时，播放指定的 `feedback`。

## 声明

```swift
nonisolated func sensoryFeedback<T>(_ feedback: SensoryFeedback, trigger: T) -> some View where T : Equatable

```

## 参数

- **feedback**：要播放的反馈类型。

- **trigger**：要监控其变化以确定何时播放的值。

## 讨论

例如，您可以设置当状态值改变时播放反馈：

```swift
struct MyView: View {
    @State private var showAccessory = false

    var body: some View {
        ContentView()
            .sensoryFeedback(.selection, trigger: showAccessory)
            .onLongPressGesture {
                showAccessory.toggle()
            }

        if showAccessory {
            AccessoryView()
        }
    }
}
```

## 提供触觉反馈

- **sensoryFeedback(trigger:_:)**：当提供的 `trigger` 值改变后，`feedback` 闭包返回时播放反馈。

- **sensoryFeedback(_:trigger:condition:)**：当提供的 `trigger` 值改变且 `condition` 闭包返回 `true` 时，播放指定的 `feedback`。

- **SensoryFeedback**：表示可以播放的触觉和/或音频反馈类型。


---
source: https://developer.apple.com/documentation/SwiftUI/View/sensoryFeedback(_:trigger:)
crawled: 2025-12-02T17:36:09Z
---

# sensoryFeedback(_:trigger:)

**Instance Method**

Plays the specified `feedback` when the provided `trigger` value changes.

## Declaration

```swift
nonisolated func sensoryFeedback<T>(_ feedback: SensoryFeedback, trigger: T) -> some View where T : Equatable

```

## Parameters

- **feedback**: Which type of feedback to play.
- **trigger**: A value to monitor for changes to determine when to play.

## Discussion

For example, you could play feedback when a state value changes:

```swift
struct MyView: View {
    @State private var showAccessory = false

    var body: some View {
        ContentView()
            .sensoryFeedback(.selection, trigger: showAccessory)
            .onLongPressGesture {
                showAccessory.toggle()
            }

        if showAccessory {
            AccessoryView()
        }
    }
}
```

## Providing haptic feedback

- **sensoryFeedback(trigger:_:)**: Plays feedback when returned from the `feedback` closure after the provided `trigger` value changes.
- **sensoryFeedback(_:trigger:condition:)**: Plays the specified `feedback` when the provided `trigger` value changes and the `condition` closure returns `true`.
- **SensoryFeedback**: Represents a type of haptic and/or audio feedback that can be played.

