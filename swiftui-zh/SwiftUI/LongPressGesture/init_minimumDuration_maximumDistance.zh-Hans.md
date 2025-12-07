---
来源：https://developer.apple.com/documentation/SwiftUI/LongPressGesture/init(minimumDuration:maximumDistance:)
抓取时间： 2025-12-03T06:43:23Z
---

# init(minimumDuration:maximumDistance:)

**Initializer**

创建一个长按手势，该手势有一个最短持续时间和一个最大移动距离，在该手势失败前交互可以移动的距离。

## 声明

```swift
init(minimumDuration: Double = 0.5, maximumDistance: CGFloat = 10)
```

## 参数

- **minimumDuration**：手势成功前长按的最短持续时间。
- **maximumDistance**：执行长按操作的手指或光标在手势失败前可移动的最大距离。

## 创建长按手势

- **init(minimumDuration:)**：创建最短持续时间的长按手势
- **minimumDuration**：手势成功前长按的最短持续时间。
- **maximumDistance**：手势失败前长按所能移动的最大距离。


---
source: https://developer.apple.com/documentation/SwiftUI/LongPressGesture/init(minimumDuration:maximumDistance:)
crawled: 2025-12-03T06:43:23Z
---

# init(minimumDuration:maximumDistance:)

**Initializer**

Creates a long-press gesture with a minimum duration and a maximum distance that the interaction can move before the gesture fails.

## Declaration

```swift
init(minimumDuration: Double = 0.5, maximumDistance: CGFloat = 10)
```

## Parameters

- **minimumDuration**: The minimum duration of the long press that must elapse before the gesture succeeds.
- **maximumDistance**: The maximum distance that the fingers or cursor performing the long press can move before the gesture fails.

## Creating a long press gesture

- **init(minimumDuration:)**: Creates a long-press gesture with a minimum duration
- **minimumDuration**: The minimum duration of the long press that must elapse before the gesture succeeds.
- **maximumDistance**: The maximum distance that the long press can move before the gesture fails.

