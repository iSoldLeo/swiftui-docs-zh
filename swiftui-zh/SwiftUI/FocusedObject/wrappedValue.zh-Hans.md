---
来源： https://developer.apple.com/documentation/SwiftUI/FocusedObject/wrappedValue
抓取时间：2025-12-03T06:48:00Z
---

# wrappedValue

**实例属性**

被聚焦对象引用的底层值。

## 声明

```swift
@MainActor @preconcurrency var wrappedValue: ObjectType? { get }
```

## 讨论

该属性提供了对值数据的主要访问权限。但是，不能直接访问 `wrappedValue`。取而代之的是使用[FocusedObject](../FocusedObject.zh-Hans.md) 属性创建的属性变量。

当可变值发生变化时，新值立即可用。但是，显示该值的视图是异步更新的，可能不会立即显示新值。

## 获取值

- **projectedValue**：聚焦对象的投影，使用动态成员查找为其属性创建绑定。
- **FocusedObject.Wrapper**：底层聚焦对象的包装器，可使用动态成员查找为其属性创建绑定。


---
source: https://developer.apple.com/documentation/SwiftUI/FocusedObject/wrappedValue
crawled: 2025-12-03T06:48:00Z
---

# wrappedValue

**Instance Property**

The underlying value referenced by the focused object.

## Declaration

```swift
@MainActor @preconcurrency var wrappedValue: ObjectType? { get }
```

## Discussion

This property provides primary access to the value’s data. However, you don’t access `wrappedValue` directly. Instead, you use the property variable created with the [FocusedObject](../FocusedObject.zh-Hans.md) attribute.

When a mutable value changes, the new value is immediately available. However, a view displaying the value is updated asynchronously and may not show the new value immediately.

## Getting the value

- **projectedValue**: A projection of the focused object that creates bindings to its properties using dynamic member lookup.
- **FocusedObject.Wrapper**: A wrapper around the underlying focused object that can create bindings to its properties using dynamic member lookup.

