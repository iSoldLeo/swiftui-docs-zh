---
来源：https://developer.apple.com/documentation/SwiftUI/LongPressGesture/init(minimumDuration:)
抓取时间： 2025-12-03T06:43:22Z
---

# init(minimumDuration:)

**Initializer**

创建具有最短持续时间的长按手势

## 声明

```swift
init(minimumDuration: Double = 0.5)
```

## 参数

- **minimumDuration**：手势成功前长按的最短持续时间。

## 创建长按手势

- **init(minimumDuration:maximumDistance:)**：创建一个长按手势，该手势有一个最短持续时间和一个最大移动距离，在该手势失败前，交互可以移动该距离。
- **minimumDuration**：手势成功前长按的最短持续时间。
- **maximumDistance**：手势失败前长按所能移动的最大距离。


---
source: https://developer.apple.com/documentation/SwiftUI/LongPressGesture/init(minimumDuration:)
crawled: 2025-12-03T06:43:22Z
---

# init(minimumDuration:)

**Initializer**

Creates a long-press gesture with a minimum duration

## Declaration

```swift
init(minimumDuration: Double = 0.5)
```

## Parameters

- **minimumDuration**: The minimum duration of the long press that must elapse before the gesture succeeds.

## Creating a long press gesture

- **init(minimumDuration:maximumDistance:)**: Creates a long-press gesture with a minimum duration and a maximum distance that the interaction can move before the gesture fails.
- **minimumDuration**: The minimum duration of the long press that must elapse before the gesture succeeds.
- **maximumDistance**: The maximum distance that the long press can move before the gesture fails.

