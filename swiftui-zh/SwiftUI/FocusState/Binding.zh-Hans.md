--- 来源：https://developer.apple.com/documentation/SwiftUI/FocusState/Binding

抓取时间：2025-12-03T04:53:41Z

---

# FocusState.Binding

**Structure**

一个属性包装类型，可以读取和写入指示当前焦点位置的值。

## 声明

```swift
@frozen @propertyWrapper struct Binding
```

## 检查绑定

- **projectedValue**：返回绑定值的绑定投影。

- **wrappedValue**：绑定属性引用的底层值。

## 检查焦点状态

- **projectedValue**：返回绑定值的焦点状态值的投影。

- **wrappedValue**：当前状态值，已考虑由于当前焦点位置而生效的任何绑定。


---
source: https://developer.apple.com/documentation/SwiftUI/FocusState/Binding
crawled: 2025-12-03T04:53:41Z
---

# FocusState.Binding

**Structure**

A property wrapper type that can read and write a value that indicates the current focus location.

## Declaration

```swift
@frozen @propertyWrapper struct Binding
```

## Inspecting the binding

- **projectedValue**: A projection of the binding value that returns a binding.
- **wrappedValue**: The underlying value referenced by the bound property.

## Inspecting the focus state

- **projectedValue**: A projection of the focus state value that returns a binding.
- **wrappedValue**: The current state value, taking into account whatever bindings might be in effect due to the current location of focus.

