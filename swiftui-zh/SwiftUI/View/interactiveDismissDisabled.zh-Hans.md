--- 来源：https://developer.apple.com/documentation/SwiftUI/View/interactiveDismissDisabled(_:)

抓取时间：2025-11-30T21:16:06Z

---

# interactiveDismissDisabled(_:)

**实例方法**

有条件地阻止交互式关闭弹出框、工作表和检查器等视图。

## 声明

```swift
nonisolated func interactiveDismissDisabled(_ isDisabled: Bool = true) -> some View

```

## 参数

- **isDisabled**：一个布尔值，指示是否阻止在工作表或弹出框中显示时以非编程方式关闭包含视图层次结构。

## 说明

用户可以使用内置手势关闭某些类型的视图。具体来说，用户可以通过向下拖动来关闭工作表，或者通过点击或轻触显示视图外部来关闭弹出框。使用 `interactiveDismissDisabled(_:)` 修饰符可以有条件地阻止此类关闭操作。通常，这样做是为了防止用户在提供所需数据或完成必要操作之前关闭演示文稿。

例如，假设您有一个视图，其中显示用户必须确认才能继续的许可协议：

```swift
struct TermsOfService: View {
    @Binding var areTermsAccepted: Bool
    @Environment(\.dismiss) private var dismiss

    var body: some View {
        Form {
            Text("License Agreement")
                .font(.title)
            Text("Terms and conditions go here.")
            Button("Accept") {
                areTermsAccepted = true
                dismiss()
            }
        }
    }
}
```

如果您在工作表中呈现此视图，用户可以通过点击按钮（该按钮会调用其 `action` 闭包中的 [dismiss](../EnvironmentValues/dismiss.zh-Hans.md)）或向下拖动工作表来关闭它。为确保用户通过点击按钮接受条款，请禁用交互式关闭功能，并根据 `areTermsAccepted` 属性进行设置：

```swift
struct ContentView: View {
    @State private var isSheetPresented = false
    @State private var areTermsAccepted = false

    var body: some View {
        Button("Use Service") {
            isSheetPresented = true
        }
        .sheet(isPresented: $isSheetPresented) {
            TermsOfService()
                .interactiveDismissDisabled(!areTermsAccepted)
        }
    }
}
```

您可以将此修饰符应用于工作表视图层级结构中的任何视图，包括工作表的顶层视图（如示例所示）或任何子视图，例如 [Form](../Form.zh-Hans.md) 或“接受”按钮 [Button](../Button.zh-Hans.md)。

此修饰符对程序化关闭无效，您可以通过更新控制呈现方式的 [Binding](../Binding.zh-Hans.md) 或调用环境的 [dismiss](../EnvironmentValues/dismiss.zh-Hans.md) 操作来触发程序化关闭。在 macOS 上，禁用弹出窗口中的交互式关闭功能会使弹出窗口变为非瞬态弹出窗口。

## 关闭演示文稿

- **isPresented**：一个布尔值，指示与此环境关联的视图当前是否处于显示状态。

- **dismiss**：关闭当前演示文稿的操作。

- **DismissAction**：关闭演示文稿的操作。


---
source: https://developer.apple.com/documentation/SwiftUI/View/interactiveDismissDisabled(_:)
crawled: 2025-11-30T21:16:06Z
---

# interactiveDismissDisabled(_:)

**Instance Method**

Conditionally prevents interactive dismissal of presentations like popovers, sheets, and inspectors.

## Declaration

```swift
nonisolated func interactiveDismissDisabled(_ isDisabled: Bool = true) -> some View

```

## Parameters

- **isDisabled**: A Boolean value that indicates whether to prevent nonprogrammatic dismissal of the containing view hierarchy when presented in a sheet or popover.

## Discussion

Users can dismiss certain kinds of presentations using built-in gestures. In particular, a user can dismiss a sheet by dragging it down, or a popover by clicking or tapping outside of the presented view. Use the `interactiveDismissDisabled(_:)` modifier to conditionally prevent this kind of dismissal. You typically do this to prevent the user from dismissing a presentation before providing needed data or completing a required action.

For instance, suppose you have a view that displays a licensing agreement that the user must acknowledge before continuing:

```swift
struct TermsOfService: View {
    @Binding var areTermsAccepted: Bool
    @Environment(\.dismiss) private var dismiss

    var body: some View {
        Form {
            Text("License Agreement")
                .font(.title)
            Text("Terms and conditions go here.")
            Button("Accept") {
                areTermsAccepted = true
                dismiss()
            }
        }
    }
}
```

If you present this view in a sheet, the user can dismiss it by either tapping the button — which calls [dismiss](../EnvironmentValues/dismiss.zh-Hans.md) from its `action` closure — or by dragging the sheet down. To ensure that the user accepts the terms by tapping the button, disable interactive dismissal, conditioned on the `areTermsAccepted` property:

```swift
struct ContentView: View {
    @State private var isSheetPresented = false
    @State private var areTermsAccepted = false

    var body: some View {
        Button("Use Service") {
            isSheetPresented = true
        }
        .sheet(isPresented: $isSheetPresented) {
            TermsOfService()
                .interactiveDismissDisabled(!areTermsAccepted)
        }
    }
}
```

You can apply the modifier to any view in the sheet’s view hierarchy, including to the sheet’s top level view, as the example demonstrates, or to any child view, like the [Form](../Form.zh-Hans.md) or the Accept [Button](../Button.zh-Hans.md).

The modifier has no effect on programmatic dismissal, which you can invoke by updating the [Binding](../Binding.zh-Hans.md) that controls the presentation, or by calling the environment’s [dismiss](../EnvironmentValues/dismiss.zh-Hans.md) action. On macOS, disabling interactive dismissal in a popover makes the popover nontransient.

## Dismissing a presentation

- **isPresented**: A Boolean value that indicates whether the view associated with this environment is currently presented.
- **dismiss**: An action that dismisses the current presentation.
- **DismissAction**: An action that dismisses a presentation.

