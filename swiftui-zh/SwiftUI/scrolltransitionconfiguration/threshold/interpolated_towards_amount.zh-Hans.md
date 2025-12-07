--- 来源：https://developer.apple.com/documentation/SwiftUI/ScrollTransitionConfiguration/Threshold/interpolated(towards:amount:)

抓取时间：2025-12-04T13:37:39Z

---

# interpolated(towards:amount:)

**实例方法**

创建一个新的阈值，该阈值结合了当前阈值和另一个阈值，并根据给定的数值进行插值。

## 声明

```swift
func interpolated(towards other: ScrollTransitionConfiguration.Threshold, amount: Double) -> ScrollTransitionConfiguration.Threshold
```

## 参数

- **other**：第二个阈值。

- **amount**：此阈值与给定阈值的组合比例，其中 0 等于此阈值，1.0 等于 `other`，介于两者之间的值表示两个阈值的组合。

## 修改阈值

- **inset(by:)**：返回一个阈值，当目标视图距离容器中心更近 `distance` 时达到该阈值。使用负值可将阈值远离中心。


---
source: https://developer.apple.com/documentation/SwiftUI/ScrollTransitionConfiguration/Threshold/interpolated(towards:amount:)
crawled: 2025-12-04T13:37:39Z
---

# interpolated(towards:amount:)

**Instance Method**

Creates a new threshold that combines this threshold value with another threshold, interpolated by the given amount.

## Declaration

```swift
func interpolated(towards other: ScrollTransitionConfiguration.Threshold, amount: Double) -> ScrollTransitionConfiguration.Threshold
```

## Parameters

- **other**: The second threshold value.
- **amount**: The ratio with which this threshold is combined with the given threshold, where zero is equal to this threshold, 1.0 is equal to `other`, and values in between combine the two thresholds.

## Modifying the threshold

- **inset(by:)**: Returns a threshold that is met when the target view is closer to the center of the container by `distance`. Use negative values to move the threshold away from the center.

