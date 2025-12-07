---
来源： https://developer.apple.com/documentation/SwiftUI/SensoryFeedback/pathComplete
抓取时间： 2025-12-03T06:22:09Z
---

# pathComplete

**类型属性**

表示绘制的路径已完成和/或已识别。

## 声明

```swift
static let pathComplete: SensoryFeedback
```

## 讨论

使用此功能可为封闭形状绘制或类似操作提供反馈。由于只有某些平台才会播放反馈，因此它应作为用户体验的补充。

仅在 iOS 上播放反馈。

## 指示更改和选择

- **alignment**：表示拖动项目的对齐方式。
- **decrease**：表示重要值下降到重要阈值以下。
- **increase**：表示重要值增加到重要临界值以上。
- **levelChange**：表示在不连续的压力等级之间移动。
- **selection**：表示 UI 元素的值正在发生变化。


---
source: https://developer.apple.com/documentation/SwiftUI/SensoryFeedback/pathComplete
crawled: 2025-12-03T06:22:09Z
---

# pathComplete

**Type Property**

Indicates a drawn path has completed and/or recognized.

## Declaration

```swift
static let pathComplete: SensoryFeedback
```

## Discussion

Use this to provide feedback for closed shape drawing or similar actions. It should supplement the user experience, since only some platforms will play feedback in response to it.

Only plays feedback on iOS.

## Indicating changes and selections

- **alignment**: Indicates the alignment of a dragged item.
- **decrease**: Indicates that an important value decreased below a significant threshold.
- **increase**: Indicates that an important value increased above a significant threshold.
- **levelChange**: Indicates movement between discrete levels of pressure.
- **selection**: Indicates that a UI element’s values are changing.

