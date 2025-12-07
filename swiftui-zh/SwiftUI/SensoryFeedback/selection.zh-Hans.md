---
来源： https://developer.apple.com/documentation/SwiftUI/SensoryFeedback/selection
抓取时间： 2025-12-03T06:22:08Z
---

# 选择

**类型属性**

表示 UI 元素的值正在发生变化。

## 声明

```swift
static let selection: SensoryFeedback
```

## 讨论

等价于 [selection(_:)](selection.zh-Hans.md) 与 `SelectionFeedback/default`。

仅在 iOS 和 watchOS 上播放反馈。

## 显示更改和选择

- **alignment**：显示拖动项目的对齐方式。
- **decrease**：表示重要值下降到重要阈值以下。
- **increase**：表示重要值增加到重要临界值以上。
- **levelChange**：表示在不连续的压力水平之间移动。
- **pathComplete**：表示绘制的路径已完成和/或已识别。


---
source: https://developer.apple.com/documentation/SwiftUI/SensoryFeedback/selection
crawled: 2025-12-03T06:22:08Z
---

# selection

**Type Property**

Indicates that a UI element’s values are changing.

## Declaration

```swift
static let selection: SensoryFeedback
```

## Discussion

Equivalent to [selection(_:)](selection.zh-Hans.md) with `SelectionFeedback/default`.

Only plays feedback on iOS and watchOS.

## Indicating changes and selections

- **alignment**: Indicates the alignment of a dragged item.
- **decrease**: Indicates that an important value decreased below a significant threshold.
- **increase**: Indicates that an important value increased above a significant threshold.
- **levelChange**: Indicates movement between discrete levels of pressure.
- **pathComplete**: Indicates a drawn path has completed and/or recognized.

