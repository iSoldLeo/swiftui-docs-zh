--- 来源：https://developer.apple.com/documentation/SwiftUI/View/accessibilityQuickAction(style:isActive:content:)

抓取时间：2025-12-02T17:43:57Z

---

# accessibilityQuickAction(style:isActive:content:)

**实例方法**

添加一个快捷操作，当系统激活时显示该操作。

## 声明

```swift
nonisolated func accessibilityQuickAction<Style, Content>(style: Style, isActive: Binding<Bool>, @ViewBuilder content: () -> Content) -> some View where Style : AccessibilityQuickActionStyle, Content : View

```

## 讨论

以下示例展示了如何使用 [prompt](../AccessibilityQuickActionStyle/prompt.zh-Hans.md) 样式添加一个用于暂停和恢复锻炼的快捷操作。

```swift
@State private var isPaused = false
@State private var isQuickActionActive = false

var body: some View {
    WorkoutView(isPaused: $isPaused)
        .accessibilityQuickAction(style: .prompt, isActive: $isQuickActionActive) {
            Button(isPaused ? "Resume" : "Pause") {
                isPaused.toggle()
            }
        }
}
```

以下示例展示了如何使用 [outline](../AccessibilityQuickActionStyle/outline.zh-Hans.md) 样式添加一个用于播放和暂停音乐的快捷操作。

```swift
@State private var isPlaying = false
@State private var isQuickActionActive = false

var body: some View {
    PlayButton(isPlaying: $isPlaying)
        .contentShape(.focusEffect, Circle())
        .accessibilityQuickAction(style: .outline, isActive: $isQuickActionActive) {
            Button(isPlaying ? "Pause" : "Play") {
                isPlaying.toggle()
            }
        }
}
```

## 为用户提供快捷操作

- **accessibilityQuickAction(style:content:)**：添加一个快捷操作，该操作会在激活时由系统显示。

- **AccessibilityQuickActionStyle**：一种描述辅助功能快捷操作显示样式的类型。


---
source: https://developer.apple.com/documentation/SwiftUI/View/accessibilityQuickAction(style:isActive:content:)
crawled: 2025-12-02T17:43:57Z
---

# accessibilityQuickAction(style:isActive:content:)

**Instance Method**

Adds a quick action to be shown by the system when active.

## Declaration

```swift
nonisolated func accessibilityQuickAction<Style, Content>(style: Style, isActive: Binding<Bool>, @ViewBuilder content: () -> Content) -> some View where Style : AccessibilityQuickActionStyle, Content : View

```

## Discussion

The following example shows how to add a quick action to pause and resume a workout, with the [prompt](../AccessibilityQuickActionStyle/prompt.zh-Hans.md) style.

```swift
@State private var isPaused = false
@State private var isQuickActionActive = false

var body: some View {
    WorkoutView(isPaused: $isPaused)
        .accessibilityQuickAction(style: .prompt, isActive: $isQuickActionActive) {
            Button(isPaused ? "Resume" : "Pause") {
                isPaused.toggle()
            }
        }
}
```

The following example shows how to add a quick action to play and pause music, with the [outline](../AccessibilityQuickActionStyle/outline.zh-Hans.md) style.

```swift
@State private var isPlaying = false
@State private var isQuickActionActive = false

var body: some View {
    PlayButton(isPlaying: $isPlaying)
        .contentShape(.focusEffect, Circle())
        .accessibilityQuickAction(style: .outline, isActive: $isQuickActionActive) {
            Button(isPlaying ? "Pause" : "Play") {
                isPlaying.toggle()
            }
        }
}
```

## Offering Quick Actions to people

- **accessibilityQuickAction(style:content:)**: Adds a quick action to be shown by the system when active.
- **AccessibilityQuickActionStyle**: A type that describes the presentation style of an accessibility quick action.

