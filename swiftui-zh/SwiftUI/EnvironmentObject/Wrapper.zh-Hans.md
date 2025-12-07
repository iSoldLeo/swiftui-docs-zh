--- 来源：https://developer.apple.com/documentation/SwiftUI/EnvironmentObject/Wrapper
抓取时间：2025-12-03T06:07:00Z

---

# EnvironmentObject.Wrapper

**Structure**

底层环境对象的包装器，可以使用动态成员查找创建与其属性的绑定。

## 声明

```swift
@MainActor @dynamicMemberLookup @frozen @preconcurrency struct Wrapper
```

## 获取绑定值

- **subscript(dynamicMember:)**：返回给定键路径的结果值的绑定。

## 获取值

- **wrappedValue**：环境对象引用的底层值。

- **projectedValue**：环境对象的投影，可以使用动态成员查找创建与其属性的绑定。

## 符合以下规范

- Sendable

- SendableMetatype


---
source: https://developer.apple.com/documentation/SwiftUI/EnvironmentObject/Wrapper
crawled: 2025-12-03T06:07:00Z
---

# EnvironmentObject.Wrapper

**Structure**

A wrapper of the underlying environment object that can create bindings to its properties using dynamic member lookup.

## Declaration

```swift
@MainActor @dynamicMemberLookup @frozen @preconcurrency struct Wrapper
```

## Getting a binding value

- **subscript(dynamicMember:)**: Returns a binding to the resulting value of a given key path.

## Getting the value

- **wrappedValue**: The underlying value referenced by the environment object.
- **projectedValue**: A projection of the environment object that creates bindings to its properties using dynamic member lookup.

## Conforms To

- Sendable
- SendableMetatype

