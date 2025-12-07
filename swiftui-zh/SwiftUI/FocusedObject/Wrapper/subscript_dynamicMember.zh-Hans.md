---
来源： https://developer.apple.com/documentation/SwiftUI/FocusedObject/Wrapper/subscript(dynamicMember:)
抓取时间： 2025-12-04T13:39:28Z
---

# subscript(dynamicMember:)

**实例下标**

返回与给定键路径值的绑定。

## 声明

```swift
@MainActor @preconcurrency subscript<T>(dynamicMember keyPath: ReferenceWritableKeyPath<ObjectType, T>) -> Binding<T> { get }
```

## 参数

- **keyPath**：指向封装对象上特定值的键路径。

## 返回值

一个新的绑定。


---
source: https://developer.apple.com/documentation/SwiftUI/FocusedObject/Wrapper/subscript(dynamicMember:)
crawled: 2025-12-04T13:39:28Z
---

# subscript(dynamicMember:)

**Instance Subscript**

Returns a binding to the value of a given key path.

## Declaration

```swift
@MainActor @preconcurrency subscript<T>(dynamicMember keyPath: ReferenceWritableKeyPath<ObjectType, T>) -> Binding<T> { get }
```

## Parameters

- **keyPath**: A key path to a specific value on the wrapped object.

## Return Value

A new binding.

