--- 来源：https://developer.apple.com/documentation/SwiftUI/AnyTransition/animation(_:)

抓取时间：2025-12-03T06:17:03Z

---

# animation(_:)

**实例方法**

为该过渡效果附加动画。

## 声明

```swift
func animation(_ animation: Animation?) -> AnyTransition
```

## 组合和配置过渡效果

- **asymmetric(insertion:removal:)**：提供一个复合过渡效果，插入和移除操作使用不同的过渡效果。

- **combined(with:)**：将此过渡效果与另一个过渡效果组合，返回一个应用了两个过渡效果的新过渡效果。


---
source: https://developer.apple.com/documentation/SwiftUI/AnyTransition/animation(_:)
crawled: 2025-12-03T06:17:03Z
---

# animation(_:)

**Instance Method**

Attaches an animation to this transition.

## Declaration

```swift
func animation(_ animation: Animation?) -> AnyTransition
```

## Combining and configuring transitions

- **asymmetric(insertion:removal:)**: Provides a composite transition that uses a different transition for insertion versus removal.
- **combined(with:)**: Combines this transition with another, returning a new transition that is the result of both transitions being applied.

