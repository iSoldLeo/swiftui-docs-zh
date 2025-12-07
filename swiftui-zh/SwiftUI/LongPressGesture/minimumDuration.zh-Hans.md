---
来源： https://developer.apple.com/documentation/SwiftUI/LongPressGesture/minimumDuration
抓取时间： 2025-12-03T06:43:23Z
---

# 最小持续时间

**实例属性**

手势成功前长按的最短持续时间。

## 声明

```swift
var minimumDuration: Double
```

## 创建长按手势

- **init(minimumDuration:)**：创建持续时间最短的长按手势
- **init(minimumDuration:maximumDistance:)**：创建一个长按手势，该手势具有最短持续时间和交互失败前可移动的最大距离。
- **maximumDistance**：长按手势失败前可移动的最大距离。


---
source: https://developer.apple.com/documentation/SwiftUI/LongPressGesture/minimumDuration
crawled: 2025-12-03T06:43:23Z
---

# minimumDuration

**Instance Property**

The minimum duration of the long press that must elapse before the gesture succeeds.

## Declaration

```swift
var minimumDuration: Double
```

## Creating a long press gesture

- **init(minimumDuration:)**: Creates a long-press gesture with a minimum duration
- **init(minimumDuration:maximumDistance:)**: Creates a long-press gesture with a minimum duration and a maximum distance that the interaction can move before the gesture fails.
- **maximumDistance**: The maximum distance that the long press can move before the gesture fails.

