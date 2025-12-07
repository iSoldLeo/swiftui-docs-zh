--- 来源：https://developer.apple.com/documentation/SwiftUI/AnyTransition/asymmetric(insertion:removal:)

抓取时间：2025-12-01T11:06:13Z

---

# asymmetric(insertion:removal:)

**类型方法**

提供一个复合过渡效果，插入和移除操作使用不同的过渡效果。

## 声明

```swift
static func asymmetric(insertion: AnyTransition, removal: AnyTransition) -> AnyTransition
```

## 组合和配置过渡效果

- **animation(_:)**：为该过渡效果附加动画。

- **combined(with:)**：将此过渡效果与另一个过渡效果组合，返回一个应用了两个过渡效果的新过渡效果。


---
source: https://developer.apple.com/documentation/SwiftUI/AnyTransition/asymmetric(insertion:removal:)
crawled: 2025-12-01T11:06:13Z
---

# asymmetric(insertion:removal:)

**Type Method**

Provides a composite transition that uses a different transition for insertion versus removal.

## Declaration

```swift
static func asymmetric(insertion: AnyTransition, removal: AnyTransition) -> AnyTransition
```

## Combining and configuring transitions

- **animation(_:)**: Attaches an animation to this transition.
- **combined(with:)**: Combines this transition with another, returning a new transition that is the result of both transitions being applied.

