---
来源： https://developer.apple.com/documentation/SwiftUI/FocusedBinding/init(_:)
抓取时间： 2025-12-01T11:37:05Z
---

# init(_:)

**Initializer**

为给定的键路径创建一个新的属性包装器。

## 声明

```swift
init(_ keyPath: KeyPath<FocusedValues, Binding<Value>?>)
```

## 参数

- **keyPath**：要读取的焦点值的关键路径。

## 讨论

属性包装器的值会随着焦点的变化和不同的已发布绑定进入或退出作用域而动态更新。


---
source: https://developer.apple.com/documentation/SwiftUI/FocusedBinding/init(_:)
crawled: 2025-12-01T11:37:05Z
---

# init(_:)

**Initializer**

A new property wrapper for the given key path.

## Declaration

```swift
init(_ keyPath: KeyPath<FocusedValues, Binding<Value>?>)
```

## Parameters

- **keyPath**: The key path for the focus value to read.

## Discussion

The value of the property wrapper is updated dynamically as focus changes and different published bindings go in and out of scope.

