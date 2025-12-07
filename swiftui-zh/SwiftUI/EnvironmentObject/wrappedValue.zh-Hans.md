--- 来源：https://developer.apple.com/documentation/SwiftUI/EnvironmentObject/wrappedValue
抓取时间：2025-12-03T06:06:58Z

---

# wrappedValue

**实例属性**

环境对象引用的底层值。

## 声明

```swift
@MainActor @preconcurrency var wrappedValue: ObjectType { get }
```

## 说明

此属性提供对值数据的主要访问。但是，您不能直接访问 `wrappedValue`。相反，您需要使用通过 [EnvironmentObject](../EnvironmentObject.zh-Hans.md) 特性创建的属性变量。

当可变值发生更改时，新值会立即生效。但是，显示该值的视图是异步更新的，可能不会立即显示新值。

## 获取值

- **projectedValue**：环境对象的投影，它使用动态成员查找创建与其属性的绑定。

- **EnvironmentObject.Wrapper**：底层环境对象的包装器，它可以使用动态成员查找创建与其属性的绑定。


---
source: https://developer.apple.com/documentation/SwiftUI/EnvironmentObject/wrappedValue
crawled: 2025-12-03T06:06:58Z
---

# wrappedValue

**Instance Property**

The underlying value referenced by the environment object.

## Declaration

```swift
@MainActor @preconcurrency var wrappedValue: ObjectType { get }
```

## Discussion

This property provides primary access to the value’s data. However, you don’t access `wrappedValue` directly. Instead, you use the property variable created with the [EnvironmentObject](../EnvironmentObject.zh-Hans.md) attribute.

When a mutable value changes, the new value is immediately available. However, a view displaying the value is updated asynchronously and may not show the new value immediately.

## Getting the value

- **projectedValue**: A projection of the environment object that creates bindings to its properties using dynamic member lookup.
- **EnvironmentObject.Wrapper**: A wrapper of the underlying environment object that can create bindings to its properties using dynamic member lookup.

