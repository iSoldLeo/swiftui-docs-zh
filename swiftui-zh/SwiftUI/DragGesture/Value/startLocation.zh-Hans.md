---
来源： https://developer.apple.com/documentation/SwiftUI/DragGesture/Value/startLocation
抓取时间： 2025-12-03T19:57:16Z
---

# 开始位置

**实例属性**

拖动手势第一个事件的位置。

## 声明

```swift
var startLocation: CGPoint
```

## 获取二维位置

- **location**：拖动手势当前事件的位置。
- **predictedEndLocation**：根据当前拖动速度，预测如果现在停止拖动，最终位置会在哪里。
- **translation**：从拖动手势开始到拖动手势当前事件之间的总平移量。
- **predictedEndTranslation**：根据当前拖动速度，预测如果现在停止拖动，最终的平移量。


---
source: https://developer.apple.com/documentation/SwiftUI/DragGesture/Value/startLocation
crawled: 2025-12-03T19:57:16Z
---

# startLocation

**Instance Property**

The location of the drag gesture’s first event.

## Declaration

```swift
var startLocation: CGPoint
```

## Getting 2D position

- **location**: The location of the drag gesture’s current event.
- **predictedEndLocation**: A prediction, based on the current drag velocity, of where the final location will be if dragging stopped now.
- **translation**: The total translation from the start of the drag gesture to the current event of the drag gesture.
- **predictedEndTranslation**: A prediction, based on the current drag velocity, of what the final translation will be if dragging stopped now.

