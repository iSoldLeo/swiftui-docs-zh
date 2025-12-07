--- 来源：https://developer.apple.com/documentation/SwiftUI/FocusedValue/wrappedValue
抓取时间：2025-12-03T06:47:49Z

---

# wrappedValue

**实例属性**

根据当前作用域和焦点视图层级的状态，获取焦点键的值。

## 声明

```swift
var wrappedValue: Value? { get }
```

## 说明

当焦点视图层级中没有任何视图导出值时，返回 `nil`。


---
source: https://developer.apple.com/documentation/SwiftUI/FocusedValue/wrappedValue
crawled: 2025-12-03T06:47:49Z
---

# wrappedValue

**Instance Property**

The value for the focus key given the current scope and state of the focused view hierarchy.

## Declaration

```swift
var wrappedValue: Value? { get }
```

## Discussion

Returns `nil` when nothing in the focused view hierarchy exports a value.

