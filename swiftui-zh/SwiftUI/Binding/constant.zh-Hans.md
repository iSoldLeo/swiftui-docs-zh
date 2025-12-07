---
来源： https://developer.apple.com/documentation/SwiftUI/Binding/constant(_:)
抓取时间： 2025-12-03T06:06:40Z
---

# constant(_:)

**类型方法**

创建一个具有不可变值的绑定。

## 声明

```swift
static func constant(_ value: Value) -> Binding<Value>
```

## 参数

- **value**：不可变值。

## 讨论

使用此方法可以创建一个不可更改的值的绑定。这在使用[PreviewProvider](../PreviewProvider.zh-Hans.md) 查看视图如何表示不同值时非常有用。

```swift
// Example of binding to an immutable value.
PlayButton(isPlaying: Binding.constant(true))
```

## 创建绑定

- **init(_:)**：通过将基值投影到哈希值来创建绑定。
- **init(projectedValue:)**：从另一个绑定的值创建一个绑定。
- **init(get:set:)**：使用读写绑定值的闭包创建绑定。


---
source: https://developer.apple.com/documentation/SwiftUI/Binding/constant(_:)
crawled: 2025-12-03T06:06:40Z
---

# constant(_:)

**Type Method**

Creates a binding with an immutable value.

## Declaration

```swift
static func constant(_ value: Value) -> Binding<Value>
```

## Parameters

- **value**: An immutable value.

## Discussion

Use this method to create a binding to a value that cannot change. This can be useful when using a [PreviewProvider](../PreviewProvider.zh-Hans.md) to see how a view represents different values.

```swift
// Example of binding to an immutable value.
PlayButton(isPlaying: Binding.constant(true))
```

## Creating a binding

- **init(_:)**: Creates a binding by projecting the base value to a hashable value.
- **init(projectedValue:)**: Creates a binding from the value of another binding.
- **init(get:set:)**: Creates a binding with closures that read and write the binding value.

