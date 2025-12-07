---
来源：https://developer.apple.com/documentation/SwiftUI/Binding/init(get:set:)
抓取时间： 2025-12-01T10:55:41Z
---

# init(get:set:)

**Initializer**

创建绑定，并使用闭包读写绑定值。

### 声明

```swift
@preconcurrency init(get: @escaping @isolated(any) () -> Value, set: @escaping @isolated(any) (Value) -> Void)
```

## 参数

- **get**：用于检索绑定值的闭包。闭包没有参数，返回一个值。
- **set**：用于设置绑定值的闭包：用于设置绑定值的闭包。闭包有以下参数：

- newValue：绑定值的新值：绑定值的新值。

## 讨论

只有当绑定值的封装类型也符合 Sendable 时，绑定才符合 Sendable。在不同并发域之间传递可发送绑定始终是安全的。不过，从不同并发域读取或写入绑定的封装值可能安全，也可能不安全，这取决于绑定是如何创建的。如果 SwiftUI 检测到绑定的使用方式可能危及数据安全，它将在运行时发出警告。

对于使用 get 和 set 闭包参数创建的 "计算 "绑定，从不同并发域访问其封装值的安全性取决于这些闭包参数是否与特定角色隔离。例如，已知（或推断）闭包参数与主行为体隔离的计算绑定只能在主行为体上访问其封装值，即使绑定也是可发送的。

## 创建绑定

- **init(_:)**：通过将基值投影到一个哈希值来创建绑定。
- **init(projectedValue:)**：从另一个绑定的值创建一个绑定。
- **constant(_:)**：创建具有不可变值的绑定。


---
source: https://developer.apple.com/documentation/SwiftUI/Binding/init(get:set:)
crawled: 2025-12-01T10:55:41Z
---

# init(get:set:)

**Initializer**

Creates a binding with closures that read and write the binding value.

## Declaration

```swift
@preconcurrency init(get: @escaping @isolated(any) () -> Value, set: @escaping @isolated(any) (Value) -> Void)
```

## Parameters

- **get**: A closure that retrieves the binding value. The closure has no parameters, and returns a value.
- **set**: A closure that sets the binding value. The closure has the following parameter:

- newValue: The new value of the binding value.

## Discussion

A binding conforms to Sendable only if its wrapped value type also conforms to Sendable. It is always safe to pass a sendable binding between different concurrency domains. However, reading from or writing to a binding’s wrapped value from a different concurrency domain may or may not be safe, depending on how the binding was created. SwiftUI will issue a warning at runtime if it detects a binding being used in a way that may compromise data safety.

For a “computed” binding created using get and set closure parameters, the safety of accessing its wrapped value from a different concurrency domain depends on whether those closure arguments are isolated to a specific actor. For example, a computed binding with closure arguments that are known (or inferred) to be isolated to the main actor must only ever access its wrapped value on the main actor as well, even if the binding is also sendable.

## Creating a binding

- **init(_:)**: Creates a binding by projecting the base value to a hashable value.
- **init(projectedValue:)**: Creates a binding from the value of another binding.
- **constant(_:)**: Creates a binding with an immutable value.

