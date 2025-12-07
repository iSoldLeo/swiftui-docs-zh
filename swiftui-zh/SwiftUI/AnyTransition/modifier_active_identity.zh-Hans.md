--- 来源：https://developer.apple.com/documentation/SwiftUI/AnyTransition/modifier(active:identity:)

抓取时间：2025-12-03T06:17:05Z

---

# modifier(active:identity:)

**类型方法**

返回在激活修饰符和标识修饰符之间定义的过渡效果。

## 声明

```swift
static func modifier<E>(active: E, identity: E) -> AnyTransition where E : ViewModifier
```

## 创建自定义过渡效果

- **init(_:)**: 创建一个实例，该实例会擦除 `transition` 的类型。


---
source: https://developer.apple.com/documentation/SwiftUI/AnyTransition/modifier(active:identity:)
crawled: 2025-12-03T06:17:05Z
---

# modifier(active:identity:)

**Type Method**

Returns a transition defined between an active modifier and an identity modifier.

## Declaration

```swift
static func modifier<E>(active: E, identity: E) -> AnyTransition where E : ViewModifier
```

## Creating a custom transition

- **init(_:)**: Create an instance that type-erases `transition`.

