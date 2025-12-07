---
来源： https://developer.apple.com/documentation/SwiftUI/DragGesture/Value/predictedEndLocation
抓取时间： 2025-12-03T19:57:18Z
---

# 预测结束位置

**实例属性**

根据当前拖动速度，预测拖动停止后的最终位置。

## 声明

```swift
var predictedEndLocation: CGPoint { get }
```

## 获取二维位置

- **startLocation**：拖动手势第一个事件的位置。
- **location**：拖动手势当前事件的位置。
- **translation**：从拖动手势开始到拖动手势当前事件的总平移量。
- **predictedEndTranslation**：根据当前拖动速度，预测如果现在停止拖动，最终的平移量。


---
source: https://developer.apple.com/documentation/SwiftUI/DragGesture/Value/predictedEndLocation
crawled: 2025-12-03T19:57:18Z
---

# predictedEndLocation

**Instance Property**

A prediction, based on the current drag velocity, of where the final location will be if dragging stopped now.

## Declaration

```swift
var predictedEndLocation: CGPoint { get }
```

## Getting 2D position

- **startLocation**: The location of the drag gesture’s first event.
- **location**: The location of the drag gesture’s current event.
- **translation**: The total translation from the start of the drag gesture to the current event of the drag gesture.
- **predictedEndTranslation**: A prediction, based on the current drag velocity, of what the final translation will be if dragging stopped now.

