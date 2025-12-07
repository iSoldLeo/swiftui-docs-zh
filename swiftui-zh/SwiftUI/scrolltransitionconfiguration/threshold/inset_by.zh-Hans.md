--- 来源：https://developer.apple.com/documentation/SwiftUI/ScrollTransitionConfiguration/Threshold/inset(by:)

抓取时间：2025-12-04T13:37:38Z

---

# inset(by:)

**实例方法**

返回一个阈值，当目标视图距离容器中心更近 `distance` 时达到该阈值。使用负值可将阈值远离中心。

## 声明

```swift
func inset(by distance: Double) -> ScrollTransitionConfiguration.Threshold
```

## 修改阈值

- **interpolated(towards:amount:)**：创建一个新的阈值，该阈值结合了当前阈值和另一个阈值，并按给定值进行插值。


---
source: https://developer.apple.com/documentation/SwiftUI/ScrollTransitionConfiguration/Threshold/inset(by:)
crawled: 2025-12-04T13:37:38Z
---

# inset(by:)

**Instance Method**

Returns a threshold that is met when the target view is closer to the center of the container by `distance`. Use negative values to move the threshold away from the center.

## Declaration

```swift
func inset(by distance: Double) -> ScrollTransitionConfiguration.Threshold
```

## Modifying the threshold

- **interpolated(towards:amount:)**: Creates a new threshold that combines this threshold value with another threshold, interpolated by the given amount.

