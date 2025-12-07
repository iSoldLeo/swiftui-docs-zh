--- 来源：https://developer.apple.com/documentation/SwiftUI/EnvironmentObject/Wrapper/subscript(dynamicMember:)

抓取时间：2025-12-04T13:10:23Z

---

# subscript(dynamicMember:)

**实例 Subscript**

返回一个绑定到给定键路径结果值的绑定。

## 声明

```swift
@MainActor @preconcurrency subscript<Subject>(dynamicMember keyPath: ReferenceWritableKeyPath<ObjectType, Subject>) -> Binding<Subject> { get }
```

## 参数

- **keyPath**：指向特定结果值的键路径。

## 返回值

一个新的绑定。


---
source: https://developer.apple.com/documentation/SwiftUI/EnvironmentObject/Wrapper/subscript(dynamicMember:)
crawled: 2025-12-04T13:10:23Z
---

# subscript(dynamicMember:)

**Instance Subscript**

Returns a binding to the resulting value of a given key path.

## Declaration

```swift
@MainActor @preconcurrency subscript<Subject>(dynamicMember keyPath: ReferenceWritableKeyPath<ObjectType, Subject>) -> Binding<Subject> { get }
```

## Parameters

- **keyPath**: A key path to a specific resulting value.

## Return Value

A new binding.

