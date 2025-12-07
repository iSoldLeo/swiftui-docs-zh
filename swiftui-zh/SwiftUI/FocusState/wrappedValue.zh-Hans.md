--- 来源：https://developer.apple.com/documentation/SwiftUI/FocusState/wrappedValue
抓取时间：2025-12-03T04:53:42Z

---

# wrappedValue

**实例属性**

当前状态值，会考虑由于当前焦点位置而生效的任何绑定。

## 声明

```swift
var wrappedValue: Value { get nonmutating set }
```

## 说明

当焦点不在任何绑定到此状态的视图中时，wrappedValue 将为 `nil`（对于可选类型状态）或 `false`（对于 `Bool` 类型状态）。

## 检查焦点状态

- **projectedValue**：焦点状态值的投影，返回一个绑定。

- **FocusState.Binding**：一种属性包装类型，可以读取和写入指示当前焦点位置的值。


---
source: https://developer.apple.com/documentation/SwiftUI/FocusState/wrappedValue
crawled: 2025-12-03T04:53:42Z
---

# wrappedValue

**Instance Property**

The current state value, taking into account whatever bindings might be in effect due to the current location of focus.

## Declaration

```swift
var wrappedValue: Value { get nonmutating set }
```

## Discussion

When focus is not in any view that is bound to this state, the wrapped value will be `nil` (for optional-typed state) or `false` (for `Bool`- typed state).

## Inspecting the focus state

- **projectedValue**: A projection of the focus state value that returns a binding.
- **FocusState.Binding**: A property wrapper type that can read and write a value that indicates the current focus location.

