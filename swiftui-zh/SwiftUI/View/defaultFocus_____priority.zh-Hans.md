--- 来源：https://developer.apple.com/documentation/SwiftUI/View/defaultFocus(_:_:priority:)

抓取时间：2025-12-02T17:43:17Z

---

# defaultFocus(_:_:priority:)

**实例方法**

定义窗口中用于评估默认焦点的区域，方法是为给定的焦点状态绑定赋值。

## 声明

```swift
nonisolated func defaultFocus<V>(_ binding: FocusState<V>.Binding, _ value: V, priority: DefaultFocusEvaluationPriority = .automatic) -> some View where V : Hashable

```

## 参数

- **binding**：在修改后的视图层次结构中评估默认焦点时要更新的焦点状态绑定。

- **value**：在评估期间要设置的绑定值。

- **priority**：指示当焦点移动到修改后的视图层次结构时，如何确定首选默认焦点目标的优先级。默认值为 `automatic`，这意味着在以编程方式初始化或重新定位焦点时，该优先级将被赋予优先权，但在响应用户导航命令时则不会。

## 返回值

修改后的视图。

## 说明

默认情况下，SwiftUI 会在窗口首次出现时以及焦点状态绑定更新自动移动焦点时评估默认焦点，但在响应用户导航命令时则不会。

客户端可以通过指定评估优先级 [userInitiated](../DefaultFocusEvaluationPriority/userInitiated.zh-Hans.md) 来覆盖默认行为，这将使 SwiftUI 在响应用户驱动的焦点导航以及自动更改时使用客户端首选的默认焦点。

在以下示例中，当视图首次显示在窗口中时，焦点会自动移动到两个文本字段中的第二个。

```swift
WindowGroup {
    VStack {
        TextField(...)
            .focused($focusedField, equals: .firstField)
        TextField(...)
            .focused($focusedField, equals: .secondField)
    }
    .defaultFocus($focusedField, .secondField)
}
```

## 控制默认焦点

- **prefersDefaultFocus(_:in:)**：指示给定命名空间下视图的默认焦点位置。

- **DefaultFocusEvaluationPriority**：在不同情况下评估焦点移动位置时，默认焦点优先级设置。


---
source: https://developer.apple.com/documentation/SwiftUI/View/defaultFocus(_:_:priority:)
crawled: 2025-12-02T17:43:17Z
---

# defaultFocus(_:_:priority:)

**Instance Method**

Defines a region of the window in which default focus is evaluated by assigning a value to a given focus state binding.

## Declaration

```swift
nonisolated func defaultFocus<V>(_ binding: FocusState<V>.Binding, _ value: V, priority: DefaultFocusEvaluationPriority = .automatic) -> some View where V : Hashable

```

## Parameters

- **binding**: A focus state binding to update when evaluating default focus in the modified view hierarchy.
- **value**: The value to set the binding to during evaluation.
- **priority**: An indication of how to prioritize the preferred default focus target when focus moves into the modified view hierarchy. The default value is `automatic`, which means the preference will be given priority when focus is being initialized or relocated programmatically, but not when responding to user-directed navigation commands.

## Return Value

The modified view.

## Discussion

By default, SwiftUI evaluates default focus when the window first appears, and when a focus state binding update moves focus automatically, but not when responding to user-driven navigation commands.

Clients can override the default behavior by specifying an evaluation priority of [userInitiated](../DefaultFocusEvaluationPriority/userInitiated.zh-Hans.md), which causes SwiftUI to use the client’s preferred default focus in response to user-driven focus navigation as well as automatic changes.

In the following example, focus automatically goes to the second of the two text fields when the view is first presented in the window.

```swift
WindowGroup {
    VStack {
        TextField(...)
            .focused($focusedField, equals: .firstField)
        TextField(...)
            .focused($focusedField, equals: .secondField)
    }
    .defaultFocus($focusedField, .secondField)
}
```

## Controlling default focus

- **prefersDefaultFocus(_:in:)**: Indicates that the view should receive focus by default for a given namespace.
- **DefaultFocusEvaluationPriority**: Prioritizations for default focus preferences when evaluating where to move focus in different circumstances.

