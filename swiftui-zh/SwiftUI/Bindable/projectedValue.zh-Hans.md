--- 来源：https://developer.apple.com/documentation/SwiftUI/Bindable/projectedValue
抓取时间：2025-12-03T06:06:36Z

---

# projectedValue

**实例属性**

可绑定对象包装器，使用动态成员查找创建与其属性的绑定。

## 声明

```swift
var projectedValue: Bindable<Value> { get }
```

## 获取值

- **wrappedValue**：包装后的对象。

- **subscript(dynamicMember:)**：返回给定键路径的值的绑定。


---
source: https://developer.apple.com/documentation/SwiftUI/Bindable/projectedValue
crawled: 2025-12-03T06:06:36Z
---

# projectedValue

**Instance Property**

The bindable wrapper for the object that creates bindings to its properties using dynamic member lookup.

## Declaration

```swift
var projectedValue: Bindable<Value> { get }
```

## Getting the value

- **wrappedValue**: The wrapped object.
- **subscript(dynamicMember:)**: Returns a binding to the value of a given key path.

