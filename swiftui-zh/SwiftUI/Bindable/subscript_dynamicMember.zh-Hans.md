--- 来源：https://developer.apple.com/documentation/SwiftUI/Bindable/subscript(dynamicMember:)

抓取时间：2025-12-03T06:06:37Z

---

# subscript(dynamicMember:)

**实例 Subscript**

返回给定键路径的值的绑定。

## 声明

```swift
subscript<Subject>(dynamicMember keyPath: ReferenceWritableKeyPath<Value, Subject>) -> Binding<Subject> { get }
```

## 获取值

- **wrappedValue**：被包装的对象。

- **projectedValue**：使用动态成员查找创建与其属性绑定的对象的可绑定包装器。


---
source: https://developer.apple.com/documentation/SwiftUI/Bindable/subscript(dynamicMember:)
crawled: 2025-12-03T06:06:37Z
---

# subscript(dynamicMember:)

**Instance Subscript**

Returns a binding to the value of a given key path.

## Declaration

```swift
subscript<Subject>(dynamicMember keyPath: ReferenceWritableKeyPath<Value, Subject>) -> Binding<Subject> { get }
```

## Getting the value

- **wrappedValue**: The wrapped object.
- **projectedValue**: The bindable wrapper for the object that creates bindings to its properties using dynamic member lookup.

