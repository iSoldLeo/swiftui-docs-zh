---
来源：https://developer.apple.com/documentation/SwiftUI/Binding/init(projectedValue:)
抓取时间：2025-12-03T06:06:38Z
---

# init(projectedValue:)

**Initializer**

根据另一个绑定的值创建一个绑定。

## 声明

```swift
init(projectedValue: Binding<Value>)
```

## 创建绑定

- **init(_:)**：通过将基值投影到哈希值来创建绑定。
- **init(get:set:)**：使用读写绑定值的闭包创建绑定。
- **constant(_:)**：创建具有不可变值的绑定。


---
source: https://developer.apple.com/documentation/SwiftUI/Binding/init(projectedValue:)
crawled: 2025-12-03T06:06:38Z
---

# init(projectedValue:)

**Initializer**

Creates a binding from the value of another binding.

## Declaration

```swift
init(projectedValue: Binding<Value>)
```

## Creating a binding

- **init(_:)**: Creates a binding by projecting the base value to a hashable value.
- **init(get:set:)**: Creates a binding with closures that read and write the binding value.
- **constant(_:)**: Creates a binding with an immutable value.

