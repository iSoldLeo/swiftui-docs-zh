---
来源： https://developer.apple.com/documentation/SwiftUI/FocusedObject/Wrapper
抓取时间： 2025-12-03T06:48:01Z
---

# FocusedObject.Wrapper

**Structure**

FocusedObject.Wrapper 是底层 FocusedObject 的包装器，可使用动态成员查找为其属性创建绑定。

### 声明

```swift
@MainActor @preconcurrency @dynamicMemberLookup @frozen struct Wrapper
```

## 访问成员

- **subscript(dynamicMember:)**：返回与给定键路径值的绑定。

## 获取值

- **projectedValue**：聚焦对象的投影，使用动态成员查找为其属性创建绑定。
- **wrappedValue**：被聚焦对象引用的底层值。


---
source: https://developer.apple.com/documentation/SwiftUI/FocusedObject/Wrapper
crawled: 2025-12-03T06:48:01Z
---

# FocusedObject.Wrapper

**Structure**

A wrapper around the underlying focused object that can create bindings to its properties using dynamic member lookup.

## Declaration

```swift
@MainActor @preconcurrency @dynamicMemberLookup @frozen struct Wrapper
```

## Accessing members

- **subscript(dynamicMember:)**: Returns a binding to the value of a given key path.

## Getting the value

- **projectedValue**: A projection of the focused object that creates bindings to its properties using dynamic member lookup.
- **wrappedValue**: The underlying value referenced by the focused object.

