--- 来源：https://developer.apple.com/documentation/SwiftUI/FocusedValue/init(_:)

抓取时间：2025-12-03T06:47:48Z

---

# init(_:)

**Initializer**

为给定的键路径创建一个新的属性包装器。

## 声明

```swift
init(_ keyPath: KeyPath<FocusedValues, Value?>)
```

## 参数

- **keyPath**：要读取的焦点值的键路径。

## 说明

属性包装器的值会随着焦点的变化以及已发布值的进入和离开作用域而动态更新。


---
source: https://developer.apple.com/documentation/SwiftUI/FocusedValue/init(_:)
crawled: 2025-12-03T06:47:48Z
---

# init(_:)

**Initializer**

A new property wrapper for the given key path.

## Declaration

```swift
init(_ keyPath: KeyPath<FocusedValues, Value?>)
```

## Parameters

- **keyPath**: The key path for the focus value to read.

## Discussion

The value of the property wrapper is updated dynamically as focus changes and different published values go in and out of scope.

