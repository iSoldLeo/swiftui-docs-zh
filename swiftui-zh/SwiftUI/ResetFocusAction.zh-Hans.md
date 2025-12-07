---
来源： https://developer.apple.com/documentation/SwiftUI/ResetFocusAction
抓取时间： 2025-12-02T17:43:19Z
---

# ResetFocusAction

**Structure**

提供重新评估默认焦点功能的环境值。

### 声明

```swift
struct ResetFocusAction
```

## 概览

获取[resetFocus](EnvironmentValues/resetFocus.zh-Hans.md) 环境值并将其作为函数调用，以便在运行时强制重新评估默认焦点。

```swift
@Namespace var mainNamespace
@Environment(\.resetFocus) var resetFocus

var body: some View {
    // ...
    resetFocus(in: mainNamespace)
    // ...
}
```

## 调用操作

- **callAsFunction(in:)**：要求焦点系统重新评估默认焦点项。

## 重置焦点

- **resetFocus**：请求焦点系统重新评估默认焦点的操作。


---
source: https://developer.apple.com/documentation/SwiftUI/ResetFocusAction
crawled: 2025-12-02T17:43:19Z
---

# ResetFocusAction

**Structure**

An environment value that provides the ability to reevaluate default focus.

## Declaration

```swift
struct ResetFocusAction
```

## Overview

Get the [resetFocus](EnvironmentValues/resetFocus.zh-Hans.md) environment value and call it as a function to force a default focus reevaluation at runtime.

```swift
@Namespace var mainNamespace
@Environment(\.resetFocus) var resetFocus

var body: some View {
    // ...
    resetFocus(in: mainNamespace)
    // ...
}
```

## Calling the action

- **callAsFunction(in:)**: Asks the focus sytem to reevaluate the default focus item.

## Resetting focus

- **resetFocus**: An action that requests the focus system to reevaluate default focus.

