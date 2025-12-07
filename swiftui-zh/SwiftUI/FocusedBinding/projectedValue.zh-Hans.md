---
来源： https://developer.apple.com/documentation/SwiftUI/FocusedBinding/projectedValue
抓取时间： 2025-12-03T06:47:57Z
---

# 预计值

**实例属性**

与可选值的绑定。

## 声明

```swift
var projectedValue: Binding<Value?> { get }
```

## 讨论

当没有聚焦视图层次结构发布相应的绑定时，解包值为`nil`。

## 获取值

- **wrappedValue**：根据当前视图层次结构的作用域和状态，焦点键的解包值。


---
source: https://developer.apple.com/documentation/SwiftUI/FocusedBinding/projectedValue
crawled: 2025-12-03T06:47:57Z
---

# projectedValue

**Instance Property**

A binding to the optional value.

## Declaration

```swift
var projectedValue: Binding<Value?> { get }
```

## Discussion

The unwrapped value is `nil` when no focused view hierarchy has published a corresponding binding.

## Getting the value

- **wrappedValue**: The unwrapped value for the focus key given the current scope and state of the focused view hierarchy.

