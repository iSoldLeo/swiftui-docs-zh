--- 来源：https://developer.apple.com/documentation/SwiftUI/AccessibilityQuickActionStyle/outline

抓取时间：2025-12-03T06:49:06Z

---

# outline

**类型属性**

一种演示样式，当辅助功能快捷操作激活时，会在视图周围添加动画轮廓。

## 声明

```swift
static var outline: AccessibilityQuickActionOutlineStyle { get }
```

## 讨论

如有必要，可以使用 [contentShape(_:_:eoFill:)](../View/contentShape_____eoFill.zh-Hans.md) 修饰符为 [focusEffect](../ContentShapeKinds/focusEffect.zh-Hans.md) 指定形状。

以下示例演示如何添加 [accessibilityQuickAction(style:content:)](../View/accessibilityQuickAction_style_content.zh-Hans.md) 来播放和暂停音乐。

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

## 获取内置菜单样式

- **prompt**：一种显示样式，当辅助功能快捷操作处于活动状态时，会向用户显示提示。


---
source: https://developer.apple.com/documentation/SwiftUI/AccessibilityQuickActionStyle/outline
crawled: 2025-12-03T06:49:06Z
---

# outline

**Type Property**

A presentation style that animates an outline around the view when the accessibility quick action is active.

## Declaration

```swift
static var outline: AccessibilityQuickActionOutlineStyle { get }
```

## Discussion

Use the [contentShape(_:_:eoFill:)](../View/contentShape_____eoFill.zh-Hans.md) modifier to provide a shape for [focusEffect](../ContentShapeKinds/focusEffect.zh-Hans.md) if necessary.

The following example shows how to add an [accessibilityQuickAction(style:content:)](../View/accessibilityQuickAction_style_content.zh-Hans.md) to play and pause music.

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

## Getting built-in menu styles

- **prompt**: A presentation style that displays a prompt to the user when the accessibility quick action is active.

