--- 来源：https://developer.apple.com/documentation/SwiftUI/View/accessibilityQuickAction(style:content:)

抓取时间：2025-11-30T21:28:55Z

---

# accessibilityQuickAction(style:content:)

**实例方法**

添加一个快捷操作，当视图处于活动状态时，系统会显示该操作。

## 声明

```swift
nonisolated func accessibilityQuickAction<Style, Content>(style: Style, @ViewBuilder content: () -> Content) -> some View where Style : AccessibilityQuickActionStyle, Content : View

```

## 说明

当视图出现时，快捷操作会自动激活。如果视图处于禁用状态，则该操作会延迟激活，直到视图不再被禁用。

以下示例展示了如何使用 [prompt](../AccessibilityQuickActionStyle/prompt.zh-Hans.md) 样式添加一个用于暂停和恢复锻炼的快捷操作。

```swift
@State private var isPaused = false

var body: some View {
    WorkoutView(isPaused: $isPaused)
        .accessibilityQuickAction(style: .prompt) {
            Button(isPaused ? "Resume" : "Pause") {
                isPaused.toggle()
            }
        }
}
```

以下示例展示了如何使用 [outline](../AccessibilityQuickActionStyle/outline.zh-Hans.md) 样式添加播放/暂停音乐的快捷操作。

```swift
@State private var isPlaying = false

var body: some View {
    PlayButton(isPlaying: $isPlaying)
        .contentShape(.focusEffect, Circle())
        .accessibilityQuickAction(style: .outline) {
            Button(isPlaying ? "Pause" : "Play") {
                isPlaying.toggle()
            }
        }
}
```

## 为用户提供快捷操作

- **accessibilityQuickAction(style:isActive:content:)**：添加一个在激活时由系统显示的快捷操作。

- **AccessibilityQuickActionStyle**：描述辅助功能快捷操作的显示样式的类型。


---
source: https://developer.apple.com/documentation/SwiftUI/View/accessibilityQuickAction(style:content:)
crawled: 2025-11-30T21:28:55Z
---

# accessibilityQuickAction(style:content:)

**Instance Method**

Adds a quick action to be shown by the system when active.

## Declaration

```swift
nonisolated func accessibilityQuickAction<Style, Content>(style: Style, @ViewBuilder content: () -> Content) -> some View where Style : AccessibilityQuickActionStyle, Content : View

```

## Discussion

The quick action will automatically become active when the view appears. If the view is disabled, the action will defer becoming active until the view is no longer disabled.

The following example shows how to add a quick action to pause and resume a workout, with the [prompt](../AccessibilityQuickActionStyle/prompt.zh-Hans.md) style.

```swift
@State private var isPaused = false

var body: some View {
    WorkoutView(isPaused: $isPaused)
        .accessibilityQuickAction(style: .prompt) {
            Button(isPaused ? "Resume" : "Pause") {
                isPaused.toggle()
            }
        }
}
```

The following example shows how to add a quick action to play and pause music, with the [outline](../AccessibilityQuickActionStyle/outline.zh-Hans.md) style.

```swift
@State private var isPlaying = false

var body: some View {
    PlayButton(isPlaying: $isPlaying)
        .contentShape(.focusEffect, Circle())
        .accessibilityQuickAction(style: .outline) {
            Button(isPlaying ? "Pause" : "Play") {
                isPlaying.toggle()
            }
        }
}
```

## Offering Quick Actions to people

- **accessibilityQuickAction(style:isActive:content:)**: Adds a quick action to be shown by the system when active.
- **AccessibilityQuickActionStyle**: A type that describes the presentation style of an accessibility quick action.

