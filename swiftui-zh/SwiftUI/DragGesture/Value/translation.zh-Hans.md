---
来源： https://developer.apple.com/documentation/SwiftUI/DragGesture/Value/translation
抓取时间： 2025-12-03T19:57:19Z
---

# 翻译

**实例属性**

从拖动手势开始到拖动手势当前事件之间的总平移量。

## 声明

```swift
var translation: CGSize { get }
```

## 讨论

这相当于 `location.{x,y} - startLocation.{x,y}`。

## 获取二维位置

- **startLocation**：拖动手势第一个事件的位置。
- **location**：拖动手势当前事件的位置。
- **predictedEndLocation**：根据当前拖动速度，预测如果现在停止拖动，最终位置会在哪里。
- **predictedEndTranslation**：根据当前拖动速度，预测如果现在停止拖动，最终平移的位置。


---
source: https://developer.apple.com/documentation/SwiftUI/DragGesture/Value/translation
crawled: 2025-12-03T19:57:19Z
---

# translation

**Instance Property**

The total translation from the start of the drag gesture to the current event of the drag gesture.

## Declaration

```swift
var translation: CGSize { get }
```

## Discussion

This is equivalent to `location.{x,y} - startLocation.{x,y}`.

## Getting 2D position

- **startLocation**: The location of the drag gesture’s first event.
- **location**: The location of the drag gesture’s current event.
- **predictedEndLocation**: A prediction, based on the current drag velocity, of where the final location will be if dragging stopped now.
- **predictedEndTranslation**: A prediction, based on the current drag velocity, of what the final translation will be if dragging stopped now.

