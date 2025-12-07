---
来源： https://developer.apple.com/documentation/swiftui/accessibilityfocusstate/wrappedvalue
抓取时间： 2025-12-04T13:40:24Z
---

# wrappedValue

**实例属性**

当前状态值，考虑了由于当前焦点位置而可能生效的任何绑定。

## 声明

```swift
var wrappedValue: Value { get nonmutating set }
```

## 讨论

当焦点不在与此状态绑定的任何视图中时，封装值将为`nil`（可选类型状态）或`false`（`Bool`- 类型状态）。

## 获取状态

- **projectedValue**：状态值的投影，可用于在视图内容和无障碍焦点位置之间建立绑定。
- **AccessibilityFocusState.Binding**


---
source: https://developer.apple.com/documentation/swiftui/accessibilityfocusstate/wrappedvalue
crawled: 2025-12-04T13:40:24Z
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

## Getting the state

- **projectedValue**: A projection of the state value that can be used to establish bindings between view content and accessibility focus placement.
- **AccessibilityFocusState.Binding**

