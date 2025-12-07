--- 来源：https://developer.apple.com/documentation/SwiftUI/EnvironmentObject/projectedValue
抓取时间：2025-12-03T06:07:00Z

---

# projectedValue

**实例属性**

环境对象的投影，它使用动态成员查找创建与其属性的绑定。

## 声明

```swift
@MainActor @preconcurrency var projectedValue: EnvironmentObject<ObjectType>.Wrapper { get }
```

## 说明

使用投影值将环境对象向下传递到视图层次结构中。

## 获取值

- **wrappedValue**：环境对象引用的底层值。

- **EnvironmentObject.Wrapper**：底层环境对象的包装器，它可以使用动态成员查找创建与其属性的绑定。


---
source: https://developer.apple.com/documentation/SwiftUI/EnvironmentObject/projectedValue
crawled: 2025-12-03T06:07:00Z
---

# projectedValue

**Instance Property**

A projection of the environment object that creates bindings to its properties using dynamic member lookup.

## Declaration

```swift
@MainActor @preconcurrency var projectedValue: EnvironmentObject<ObjectType>.Wrapper { get }
```

## Discussion

Use the projected value to pass an environment object down a view hierarchy.

## Getting the value

- **wrappedValue**: The underlying value referenced by the environment object.
- **EnvironmentObject.Wrapper**: A wrapper of the underlying environment object that can create bindings to its properties using dynamic member lookup.

