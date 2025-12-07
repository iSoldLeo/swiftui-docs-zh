---
来源： https://developer.apple.com/documentation/SwiftUI/ObservedObject/Wrapper/subscript(dynamicMember:)
抓取时间： 2025-12-03T17:21:11Z
---

# subscript(dynamicMember:)

**实例下标**

获取与指定键路径值的绑定。

## 声明

```swift
@MainActor @preconcurrency subscript<Subject>(dynamicMember keyPath: ReferenceWritableKeyPath<ObjectType, Subject>) -> Binding<Subject> { get }
```

## 参数

- **keyPath**：指向特定值的关键路径。

## 返回值

一个新的绑定。


---
source: https://developer.apple.com/documentation/SwiftUI/ObservedObject/Wrapper/subscript(dynamicMember:)
crawled: 2025-12-03T17:21:11Z
---

# subscript(dynamicMember:)

**Instance Subscript**

Gets a binding to the value of a specified key path.

## Declaration

```swift
@MainActor @preconcurrency subscript<Subject>(dynamicMember keyPath: ReferenceWritableKeyPath<ObjectType, Subject>) -> Binding<Subject> { get }
```

## Parameters

- **keyPath**: A key path to a specific  value.

## Return Value

A new binding.

