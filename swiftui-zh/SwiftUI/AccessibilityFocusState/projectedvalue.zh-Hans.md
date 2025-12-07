---
来源： https://developer.apple.com/documentation/swiftui/accessibilityfocusstate/projectedvalue
抓取时间： 2025-12-04T13:40:23Z
---

# 预计值

**实例属性**

状态值的投影，可用于在视图内容和无障碍焦点位置之间建立绑定。

## 声明

```swift
var projectedValue: AccessibilityFocusState<Value>.Binding { get }
```

## 讨论

将 `projectedValue` 与 [accessibilityFocused(_:equals:)](../View/accessibilityFocused___equals.zh-Hans.md) 结合使用，可在视图内容和无障碍焦点位置之间建立绑定。

## 获取状态

- **wrappedValue**：当前状态值，并考虑到由于当前焦点位置而可能生效的任何绑定。
- **AccessibilityFocusState.Binding**：当前状态值。


---
source: https://developer.apple.com/documentation/swiftui/accessibilityfocusstate/projectedvalue
crawled: 2025-12-04T13:40:23Z
---

# projectedValue

**Instance Property**

A projection of the state value that can be used to establish bindings between view content and accessibility focus placement.

## Declaration

```swift
var projectedValue: AccessibilityFocusState<Value>.Binding { get }
```

## Discussion

Use `projectedValue` in conjunction with [accessibilityFocused(_:equals:)](../View/accessibilityFocused___equals.zh-Hans.md) to establish bindings between view content and accessibility focus placement.

## Getting the state

- **wrappedValue**: The current state value, taking into account whatever bindings might be in effect due to the current location of focus.
- **AccessibilityFocusState.Binding**

