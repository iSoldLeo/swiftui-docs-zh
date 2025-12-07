---
来源： https://developer.apple.com/documentation/swiftui/observedobject/wrapper
抓取时间： 2025-12-04T13:07:54Z
---

# ObservedObject.Wrapper

**Structure**

底层可观察对象的包装器，可创建与其属性的绑定。

## 声明

```swift
@MainActor @dynamicMemberLookup @preconcurrency @frozen struct Wrapper
```

## 下标

- **subscript(dynamicMember:)**：获取与指定键路径值的绑定。

## 获取值

- **wrappedValue**：观察对象引用的底层值。
- **projectedValue**：被观测对象的投影，用于创建与其属性的绑定。

## 符合

- 可发送
- 可发送元类型


---
source: https://developer.apple.com/documentation/swiftui/observedobject/wrapper
crawled: 2025-12-04T13:07:54Z
---

# ObservedObject.Wrapper

**Structure**

A wrapper of the underlying observable object that can create bindings to its properties.

## Declaration

```swift
@MainActor @dynamicMemberLookup @preconcurrency @frozen struct Wrapper
```

## Subscripts

- **subscript(dynamicMember:)**: Gets a binding to the value of a specified key path.

## Getting the value

- **wrappedValue**: The underlying value that the observed object references.
- **projectedValue**: A projection of the observed object that creates bindings to its properties.

## Conforms To

- Sendable
- SendableMetatype

