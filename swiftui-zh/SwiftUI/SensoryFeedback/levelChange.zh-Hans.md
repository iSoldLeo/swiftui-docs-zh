---
来源： https://developer.apple.com/documentation/SwiftUI/SensoryFeedback/levelChange
抓取时间： 2025-12-03T06:22:08Z
---

# 等级变更

**类型属性**

表示压力在不同级别之间的变化。

## 声明

```swift
static let levelChange: SensoryFeedback
```

## 讨论

例如，当用户按下视频播放器上的快进按钮时，播放速度可能会增加或减少，当压力达到不同程度时，就会提供触觉反馈。

仅在 macOS 上播放反馈。

##显示更改和选择

- **alignment**：显示拖动项目的对齐方式。
- **decrease**：表示重要值下降到重要阈值以下。
- **increase**：表示重要值增加到重要临界值以上。
- **selection**：表示 UI 元素的值正在发生变化。
- **pathComplete**：表示绘制的路径已完成和/或已识别。


---
source: https://developer.apple.com/documentation/SwiftUI/SensoryFeedback/levelChange
crawled: 2025-12-03T06:22:08Z
---

# levelChange

**Type Property**

Indicates movement between discrete levels of pressure.

## Declaration

```swift
static let levelChange: SensoryFeedback
```

## Discussion

For example, as the user presses a fast-forward button on a video player, playback could increase or decrease and haptic feedback could be provided as different levels of pressure are reached.

Only plays feedback on macOS.

## Indicating changes and selections

- **alignment**: Indicates the alignment of a dragged item.
- **decrease**: Indicates that an important value decreased below a significant threshold.
- **increase**: Indicates that an important value increased above a significant threshold.
- **selection**: Indicates that a UI element’s values are changing.
- **pathComplete**: Indicates a drawn path has completed and/or recognized.

