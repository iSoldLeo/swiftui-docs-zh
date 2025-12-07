--- 来源：https://developer.apple.com/documentation/SwiftUI/View/prefersDefaultFocus(_:in:)

抓取时间：2025-11-30T21:28:17Z

---

# prefersDefaultFocus(_:in:)

**实例方法**

指示视图是否应默认获得给定命名空间的焦点。

## 声明

```swift
nonisolated func prefersDefaultFocus(_ prefersDefaultFocus: Bool = true, in namespace: Namespace.ID) -> some View

```

## 参数

- **prefersDefaultFocus**：一个布尔值，指示此视图是否默认获得焦点。默认值 `true` 表示视图默认获得焦点。

- **namespace**：与此视图默认获得焦点的焦点作用域关联的命名空间。

## 返回值

一个修改后的视图，用于设置其是否默认获得焦点。

## 说明

此修饰符用于设置当没有其他视图获得焦点时，该视图的初始焦点优先级。使用环境值 [resetFocus](../EnvironmentValues/resetFocus.zh-Hans.md) 可以随时强制重新评估默认焦点。

以下 tvOS 示例在 [VStack](../VStack.zh-Hans.md) 中显示了三个按钮，分别标记为“1”、“2”和“3”。默认情况下，“1”按钮会获得焦点，因为它位于堆栈中的第一个子视图。但是，修饰符 `prefersDefaultFocus(_:in:)` 允许按钮“3”获得默认焦点。按钮可见后，用户可以向下滚动并选中“重置为默认焦点”按钮。当用户激活此按钮时，它会使用 [ResetFocusAction](../ResetFocusAction.zh-Hans.md) 重新评估 `mainNamespace` 中的默认焦点，从而将焦点返回到按钮“3”。

```swift
struct ContentView: View {
    @Namespace var mainNamespace
    @Environment(\.resetFocus) var resetFocus

    var body: some View {
        VStack {
            Button ("1") {}
            Button ("2") {}
            Button ("3") {}
                .prefersDefaultFocus(in: mainNamespace)
            Button ("Reset to default focus") {
                resetFocus(in: mainNamespace)
            }
        }
        .focusScope(mainNamespace)
    }
}
```

默认焦点偏好仅限于与提供的命名空间匹配的可聚焦祖先元素。如果多个视图都表达了此偏好，则 SwiftUI 会应用当前平台规则来确定哪个视图获得焦点。

## 控制默认焦点

- **defaultFocus(_:_:priority:)**：通过为给定的焦点状态绑定赋值，定义用于评估默认焦点的窗口区域。

- **DefaultFocusEvaluationPriority**：在不同情况下评估焦点移动位置时，默认焦点偏好的优先级。


---
source: https://developer.apple.com/documentation/SwiftUI/View/prefersDefaultFocus(_:in:)
crawled: 2025-11-30T21:28:17Z
---

# prefersDefaultFocus(_:in:)

**Instance Method**

Indicates that the view should receive focus by default for a given namespace.

## Declaration

```swift
nonisolated func prefersDefaultFocus(_ prefersDefaultFocus: Bool = true, in namespace: Namespace.ID) -> some View

```

## Parameters

- **prefersDefaultFocus**: A Boolean value that indicates whether this view prefers to receive focus by default. The default value, `true`, causes the view to receive focus by default.
- **namespace**: The namespace associated with the focus scope within which this view prefers default focus.

## Return Value

A modified view that sets whether it prefers to be focused by default.

## Discussion

This modifier sets the initial focus preference when no other view has focus. Use the environment value [resetFocus](../EnvironmentValues/resetFocus.zh-Hans.md) to force a reevaluation of default focus at any time.

The following tvOS example shows three buttons, labeled “1”, “2”, and “3”, in a [VStack](../VStack.zh-Hans.md). By default, the “1” button would receive focus, because it is the first child in the stack. However, the `prefersDefaultFocus(_:in:)` modifier allows button “3” to receive default focus instead. Once the buttons are visible, the user can move down to and focus the “Reset to default focus” button. When the user activates this button, it uses the [ResetFocusAction](../ResetFocusAction.zh-Hans.md) to reevaluate default focus in the `mainNamespace`, which returns the focus to button “3”.

```swift
struct ContentView: View {
    @Namespace var mainNamespace
    @Environment(\.resetFocus) var resetFocus

    var body: some View {
        VStack {
            Button ("1") {}
            Button ("2") {}
            Button ("3") {}
                .prefersDefaultFocus(in: mainNamespace)
            Button ("Reset to default focus") {
                resetFocus(in: mainNamespace)
            }
        }
        .focusScope(mainNamespace)
    }
}
```

The default focus preference is limited to the focusable ancestor that matches the provided namespace. If multiple views express this preference, then SwiftUI applies the current platform rules to determine which view receives focus.

## Controlling default focus

- **defaultFocus(_:_:priority:)**: Defines a region of the window in which default focus is evaluated by assigning a value to a given focus state binding.
- **DefaultFocusEvaluationPriority**: Prioritizations for default focus preferences when evaluating where to move focus in different circumstances.

