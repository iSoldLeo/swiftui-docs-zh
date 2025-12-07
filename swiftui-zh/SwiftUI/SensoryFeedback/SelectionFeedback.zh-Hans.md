---
来源： https://developer.apple.com/documentation/SwiftUI/SensoryFeedback/SelectionFeedback
抓取时间： 2025-12-03T06:22:19Z
---

# SensoryFeedback.SelectionFeedback

**Structure**

可在特定 UI 元素的值发生变化时播放的反馈。

## 声明

```swift
struct SelectionFeedback
```

## 类型属性

- **maximum**：表示已达到控件的最大值，例如当滑块的拇指拖动到滑块的最大值时。
- **minimum**：表示已达到控件的最小值，例如当滑块的拇指被拖动到滑块的最小值时。
- **off**：表示控件的值已变为关闭，例如当释放并关闭切换开关时。
- **on**：表示控件的值已变为打开，例如点击切换按钮打开时。

## 符合

- 等价
- 可散列
- 可发送
- 可发送元类型


---
source: https://developer.apple.com/documentation/SwiftUI/SensoryFeedback/SelectionFeedback
crawled: 2025-12-03T06:22:19Z
---

# SensoryFeedback.SelectionFeedback

**Structure**

Feedback that can be played in response to a specific UI element’s values changing.

## Declaration

```swift
struct SelectionFeedback
```

## Type Properties

- **maximum**: Indicates that a control’s maximum value has been reached, such as when a slider’s thumb is dragged to the slider’s maximum value.
- **minimum**: Indicates that a control’s minimum value has been reached, such as when a slider’s thumb is dragged to the slider’s minimum value.
- **off**: Indicates that a control’s value has changed to off, such as when a toggle is released and turned off.
- **on**: Indicates that a control’s value has changed to on, such as when a toggle is tapped to turn on.

## Conforms To

- Equatable
- Hashable
- Sendable
- SendableMetatype

