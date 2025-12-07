---
来源： https://developer.apple.com/documentation/SwiftUI/Binding/init(_:)
抓取时间： 2025-12-01T10:55:39Z
---

# init(_:)

**Initializer**

通过将基值投影到哈希值来创建绑定。

## 声明

```swift
init<V>(_ base: Binding<V>) where Value == AnyHashable, V : Hashable
```

## 参数

- **base**：投影到`Hashable` 值的`AnyHashable` 值。

## 创建绑定

- **init(projectedValue:)**：从另一个绑定的值创建一个绑定。
- **init(get:set:)**：使用读写绑定值的闭包创建绑定。
- **constant(_:)**：创建具有不可变值的绑定。


---
source: https://developer.apple.com/documentation/SwiftUI/Binding/init(_:)
crawled: 2025-12-01T10:55:39Z
---

# init(_:)

**Initializer**

Creates a binding by projecting the base value to a hashable value.

## Declaration

```swift
init<V>(_ base: Binding<V>) where Value == AnyHashable, V : Hashable
```

## Parameters

- **base**: A `Hashable` value to project to an `AnyHashable` value.

## Creating a binding

- **init(projectedValue:)**: Creates a binding from the value of another binding.
- **init(get:set:)**: Creates a binding with closures that read and write the binding value.
- **constant(_:)**: Creates a binding with an immutable value.

