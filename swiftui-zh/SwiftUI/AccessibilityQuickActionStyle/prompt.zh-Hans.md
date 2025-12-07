--- 来源：https://developer.apple.com/documentation/SwiftUI/AccessibilityQuickActionStyle/prompt
抓取时间：2025-12-03T06:49:07Z

---

# prompt

**类型属性**

一种显示样式，用于在辅助功能快捷操作激活时向用户显示提示。

## 声明

```swift
static var prompt: AccessibilityQuickActionPromptStyle { get }
```

## 讨论

以下示例展示了如何添加 [accessibilityQuickAction(style:content:)](../View/accessibilityQuickAction_style_content.zh-Hans.md) 来暂停和恢复锻炼。

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

## 获取内置菜单样式

- **outline**：一种显示样式，用于在辅助功能快捷操作激活时为视图添加动画轮廓。


---
source: https://developer.apple.com/documentation/SwiftUI/AccessibilityQuickActionStyle/prompt
crawled: 2025-12-03T06:49:07Z
---

# prompt

**Type Property**

A presentation style that displays a prompt to the user when the accessibility quick action is active.

## Declaration

```swift
static var prompt: AccessibilityQuickActionPromptStyle { get }
```

## Discussion

The following example shows how to add an [accessibilityQuickAction(style:content:)](../View/accessibilityQuickAction_style_content.zh-Hans.md) to pause and resume a workout.

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

## Getting built-in menu styles

- **outline**: A presentation style that animates an outline around the view when the accessibility quick action is active.

