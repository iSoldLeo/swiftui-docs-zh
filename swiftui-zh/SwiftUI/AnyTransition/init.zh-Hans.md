--- 来源：https://developer.apple.com/documentation/SwiftUI/AnyTransition/init(_:)

抓取时间：2025-12-03T06:17:05Z

---

# init(_:)

**Initializer**

创建一个实例，该实例会擦除 `transition` 的类型。

## 声明

```swift
init<T>(_ transition: T) where T : Transition
```

## 创建自定义过渡

- **modifier(active:identity:)**：返回在活动修饰符和标识修饰符之间定义的过渡。


---
source: https://developer.apple.com/documentation/SwiftUI/AnyTransition/init(_:)
crawled: 2025-12-03T06:17:05Z
---

# init(_:)

**Initializer**

Create an instance that type-erases `transition`.

## Declaration

```swift
init<T>(_ transition: T) where T : Transition
```

## Creating a custom transition

- **modifier(active:identity:)**: Returns a transition defined between an active modifier and an identity modifier.

