---
来源： https://developer.apple.com/documentation/SwiftUI/SensoryFeedback/alignment
抓取时间： 2025-12-03T06:22:05Z
---

# 对齐

**类型属性**

表示拖动项目的对齐方式。

## 声明

```swift
static let alignment: SensoryFeedback
```

## 讨论

例如，当用户拖动一个形状与另一个形状对齐时，可以在绘图应用程序中使用此模式。

仅在 iOS 和 macOS 上播放反馈。

## 指示更改和选择

- **decrease**：表示重要值下降到重要阈值以下。
- **increase**：表示重要值增加到重要临界值以上。
- **levelChange**：表示在不连续的压力水平之间移动。
- **selection**：表示 UI 元素的值正在发生变化。
- **pathComplete**：表示绘制的路径已完成和/或已识别。


---
source: https://developer.apple.com/documentation/SwiftUI/SensoryFeedback/alignment
crawled: 2025-12-03T06:22:05Z
---

# alignment

**Type Property**

Indicates the alignment of a dragged item.

## Declaration

```swift
static let alignment: SensoryFeedback
```

## Discussion

For example, use this pattern in a drawing app when the user drags a shape into alignment with another shape.

Only plays feedback on iOS and macOS.

## Indicating changes and selections

- **decrease**: Indicates that an important value decreased below a significant threshold.
- **increase**: Indicates that an important value increased above a significant threshold.
- **levelChange**: Indicates movement between discrete levels of pressure.
- **selection**: Indicates that a UI element’s values are changing.
- **pathComplete**: Indicates a drawn path has completed and/or recognized.

