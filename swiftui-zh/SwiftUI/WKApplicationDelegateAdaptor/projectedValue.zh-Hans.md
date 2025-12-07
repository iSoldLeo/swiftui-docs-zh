--- 来源：https://developer.apple.com/documentation/SwiftUI/WKApplicationDelegateAdaptor/projectedValue
抓取时间：2025-12-03T05:30:55Z

---

# projectedValue

**实例属性**

投影对象，使用动态成员查找创建与其属性的绑定。

## 声明

```swift
@MainActor @preconcurrency var projectedValue: ObservedObject<DelegateType>.Wrapper { get }
```

## 说明

使用投影值将绑定值传递到视图层次结构中。要获取 `projectedValue`，请在属性变量前加上 `$`。

## 获取委托适配器

- **wrappedValue**：底层委托。


---
source: https://developer.apple.com/documentation/SwiftUI/WKApplicationDelegateAdaptor/projectedValue
crawled: 2025-12-03T05:30:55Z
---

# projectedValue

**Instance Property**

A projection of the observed object that creates bindings to its properties using dynamic member lookup.

## Declaration

```swift
@MainActor @preconcurrency var projectedValue: ObservedObject<DelegateType>.Wrapper { get }
```

## Discussion

Use the projected value to pass a binding value down a view hierarchy. To get the `projectedValue`, prefix the property variable with `$`.

## Getting the delegate adaptor

- **wrappedValue**: The underlying delegate.

