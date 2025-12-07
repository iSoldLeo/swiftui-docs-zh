---
来源： https://developer.apple.com/documentation/SwiftUI/FocusedObject/projectedValue
抓取时间：2025-12-03T06:48:00Z
---

# 预计值

**实例属性**

聚焦对象的投影，通过动态成员查找与其属性绑定。

## 声明

```swift
@MainActor @preconcurrency var projectedValue: FocusedObject<ObjectType>.Wrapper? { get }
```

## 讨论

使用投影值可将聚焦对象向下传递到视图层次结构中。

## 获取值

- **wrappedValue**：被聚焦对象引用的底层值。
- **FocusedObject.Wrapper**：围绕底层聚焦对象的包装器，可使用动态成员查找功能创建与其属性的绑定。


---
source: https://developer.apple.com/documentation/SwiftUI/FocusedObject/projectedValue
crawled: 2025-12-03T06:48:00Z
---

# projectedValue

**Instance Property**

A projection of the focused object that creates bindings to its properties using dynamic member lookup.

## Declaration

```swift
@MainActor @preconcurrency var projectedValue: FocusedObject<ObjectType>.Wrapper? { get }
```

## Discussion

Use the projected value to pass a focused object down a view hierarchy.

## Getting the value

- **wrappedValue**: The underlying value referenced by the focused object.
- **FocusedObject.Wrapper**: A wrapper around the underlying focused object that can create bindings to its properties using dynamic member lookup.

