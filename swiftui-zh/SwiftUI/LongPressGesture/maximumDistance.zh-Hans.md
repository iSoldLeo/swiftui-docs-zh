---
来源： https://developer.apple.com/documentation/SwiftUI/LongPressGesture/maximumDistance
抓取时间： 2025-12-03T06:43:24Z
---

# 最大距离

**实例属性**

长按手势失败前的最大移动距离。

## 声明

```swift
var maximumDistance: CGFloat { get set }
```

## 创建长按手势

- **init(minimumDuration:)**：创建持续时间最短的长按手势
- **init(minimumDuration:maximumDistance:)**：创建一个长按手势，该手势具有最短持续时间和交互失败前可移动的最大距离。
- **minimumDuration**：长按手势成功前必须经过的最短持续时间。


---
source: https://developer.apple.com/documentation/SwiftUI/LongPressGesture/maximumDistance
crawled: 2025-12-03T06:43:24Z
---

# maximumDistance

**Instance Property**

The maximum distance that the long press can move before the gesture fails.

## Declaration

```swift
var maximumDistance: CGFloat { get set }
```

## Creating a long press gesture

- **init(minimumDuration:)**: Creates a long-press gesture with a minimum duration
- **init(minimumDuration:maximumDistance:)**: Creates a long-press gesture with a minimum duration and a maximum distance that the interaction can move before the gesture fails.
- **minimumDuration**: The minimum duration of the long press that must elapse before the gesture succeeds.

