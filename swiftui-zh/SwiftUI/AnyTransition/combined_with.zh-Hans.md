--- 来源：https://developer.apple.com/documentation/SwiftUI/AnyTransition/combined(with:)

抓取时间：2025-12-03T06:17:04Z

---

# combined(with:)

**实例方法**

将此过渡效果与另一个过渡效果组合，返回一个融合了两个过渡效果的新过渡效果。

## 声明

```swift
func combined(with other: AnyTransition) -> AnyTransition
```

## 组合和配置过渡效果

- **animation(_:)**：为该过渡效果附加动画。

- **asymmetric(insertion:removal:)**：提供一个复合过渡效果，插入和移除操作使用不同的过渡效果。


---
source: https://developer.apple.com/documentation/SwiftUI/AnyTransition/combined(with:)
crawled: 2025-12-03T06:17:04Z
---

# combined(with:)

**Instance Method**

Combines this transition with another, returning a new transition that is the result of both transitions being applied.

## Declaration

```swift
func combined(with other: AnyTransition) -> AnyTransition
```

## Combining and configuring transitions

- **animation(_:)**: Attaches an animation to this transition.
- **asymmetric(insertion:removal:)**: Provides a composite transition that uses a different transition for insertion versus removal.

