---
来源： https://developer.apple.com/documentation/SwiftUI/EnvironmentValues/resetFocus
抓取时间： 2025-12-02T17:43:18Z
---

# 重置焦点

**实例属性**

请求焦点系统重新评估默认焦点的操作。

## 声明

```swift
var resetFocus: ResetFocusAction { get }
```

## 讨论

获取此环境值，并将其作为函数调用，以便在运行时强制重新评估默认焦点。

```swift
@Namespace var mainNamespace
@Environment(\.resetFocus) var resetFocus

var body: some View {
    // ...
    resetFocus(in: mainNamespace)
    // ...
}
```

## 重置焦点

- **ResetFocusAction**：提供重新评估默认焦点功能的环境值。


---
source: https://developer.apple.com/documentation/SwiftUI/EnvironmentValues/resetFocus
crawled: 2025-12-02T17:43:18Z
---

# resetFocus

**Instance Property**

An action that requests the focus system to reevaluate default focus.

## Declaration

```swift
var resetFocus: ResetFocusAction { get }
```

## Discussion

Get this environment value and call and call it as a function to force a default focus reevaluation at runtime.

```swift
@Namespace var mainNamespace
@Environment(\.resetFocus) var resetFocus

var body: some View {
    // ...
    resetFocus(in: mainNamespace)
    // ...
}
```

## Resetting focus

- **ResetFocusAction**: An environment value that provides the ability to reevaluate default focus.

