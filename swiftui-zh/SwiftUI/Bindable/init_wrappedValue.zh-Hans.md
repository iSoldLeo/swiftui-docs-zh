--- 来源：https://developer.apple.com/documentation/SwiftUI/Bindable/init(wrappedValue:)

抓取时间：2025-12-03T06:06:34Z

---

# init(wrappedValue:)

**Initializer**

从可观察对象创建可绑定对象。

## 声明

```swift
init(wrappedValue: Value)
```

## 讨论

您不应该直接调用此初始化器。而是声明一个带有 `@Bindable` 特性的属性，并提供一个初始值。

## 创建可绑定值

- **init(_:)**：从可观察对象创建可绑定对象。

- **init(projectedValue:)**：从另一个可绑定对象的值创建可绑定对象。


---
source: https://developer.apple.com/documentation/SwiftUI/Bindable/init(wrappedValue:)
crawled: 2025-12-03T06:06:34Z
---

# init(wrappedValue:)

**Initializer**

Creates a bindable object from an observable object.

## Declaration

```swift
init(wrappedValue: Value)
```

## Discussion

You should not call this initializer directly. Instead, declare a property with the `@Bindable` attribute, and provide an initial value.

## Creating a bindable value

- **init(_:)**: Creates a bindable object from an observable object.
- **init(projectedValue:)**: Creates a bindable from the value of another bindable.

