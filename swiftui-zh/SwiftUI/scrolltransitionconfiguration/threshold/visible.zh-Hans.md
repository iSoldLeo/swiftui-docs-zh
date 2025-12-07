--- 来源：https://developer.apple.com/documentation/SwiftUI/ScrollTransitionConfiguration/Threshold/visible(_:)

抓取时间：2025-12-04T13:37:38Z

---

# visible(_:)

**类型方法**

目标视图的可见度由给定值决定，其中 0 表示完全隐藏，1 表示完全可见。

## 声明

```swift
static func visible(_ amount: Double) -> ScrollTransitionConfiguration.Threshold
```

## 说明

小于 0 或大于 1 的值会被限制。

## 获取阈值

- **centered**：目标视图在容器内居中显示

- **hidden**

- **visible**


---
source: https://developer.apple.com/documentation/SwiftUI/ScrollTransitionConfiguration/Threshold/visible(_:)
crawled: 2025-12-04T13:37:38Z
---

# visible(_:)

**Type Method**

The target view is visible by the given amount, where zero is fully hidden, and one is fully visible.

## Declaration

```swift
static func visible(_ amount: Double) -> ScrollTransitionConfiguration.Threshold
```

## Discussion

Values less than zero or greater than one are clamped.

## Getting the threshold

- **centered**: The target view is centered within the container
- **hidden**
- **visible**

