--- 来源：https://developer.apple.com/documentation/SwiftUI/View/accessibilityDefaultFocus(_:_:)

抓取时间：2025-11-30T21:07:25Z

---

# accessibilityDefaultFocus(_:_:)

**实例方法**

定义一个区域，通过为给定的辅助功能焦点状态绑定赋值来评估默认辅助功能焦点。

## 声明

```swift
nonisolated func accessibilityDefaultFocus<Value>(_ binding: AccessibilityFocusState<Value>.Binding, _ value: Value) -> some View where Value : Hashable

```

## 参数

- **binding**：评估默认辅助功能焦点时要更新的辅助功能焦点状态绑定。

- **value**：评估期间要设置的绑定值。

## 讨论

辅助功能默认焦点会在以下情况下进行评估：场景出现且 VoiceOver 等辅助功能技术聚焦于其内容；辅助功能焦点状态绑定更新自动移动焦点；以及场景布局发生变化且辅助功能技术必须重新聚焦于新内容。

在以下示例中，VoiceOver 等辅助功能技术会自动将焦点落在播放列表标题上，因为这是初始焦点最重要的视图，而无需浏览所有控件来了解视图的主要内容。

```swift
var body: some View {
    VStack {
        PlayerControls(currentSong: $currentSong)
        Text(playlist.title)
            .font(.title)
            .accessibilityFocused($focusedField, equals: .title)
        PlaylistEntries(entries: playlist.entries)
    }
    .accessibilityDefaultFocus($focusedField, .title)
}
```


---
source: https://developer.apple.com/documentation/SwiftUI/View/accessibilityDefaultFocus(_:_:)
crawled: 2025-11-30T21:07:25Z
---

# accessibilityDefaultFocus(_:_:)

**Instance Method**

Defines a region in which default accessibility focus is evaluated by assigning a value to a given accessibility focus state binding.

## Declaration

```swift
nonisolated func accessibilityDefaultFocus<Value>(_ binding: AccessibilityFocusState<Value>.Binding, _ value: Value) -> some View where Value : Hashable

```

## Parameters

- **binding**: An accessibility focus state binding to update when evaluating default accessibility focus.
- **value**: The value to set the binding to during evaluation.

## Discussion

Accessibility default focus is evaluated when a scene appears and an accessibility technology like VoiceOver focuses on its content, when an accessibility focus state binding update moves focus automatically, and when the layout of a scene changes and the accessibility technology must refocus on new content.

In the following example, an accessibility technology, like VoiceOver, automatically lands on the title of the playlist as the most important view to initially have focus on, rather than navigating through all controls to understand what the primary content of the view is.

```swift
var body: some View {
    VStack {
        PlayerControls(currentSong: $currentSong)
        Text(playlist.title)
            .font(.title)
            .accessibilityFocused($focusedField, equals: .title)
        PlaylistEntries(entries: playlist.entries)
    }
    .accessibilityDefaultFocus($focusedField, .title)
}
```

