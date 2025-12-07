--- 来源：https://developer.apple.com/documentation/SwiftUI/View/alert(_:isPresented:actions:)

抓取时间：2025-12-02T17:30:24Z

---

# alert(_:isPresented:actions:)

**实例方法**

当给定条件为真时，显示一个提示框，标题使用文本视图。

## 声明

```swift
nonisolated func alert<A>(_ title: Text, isPresented: Binding<Bool>, @ViewBuilder actions: () -> A) -> some View where A : View

```

## 参数

- **title**：提示框的标题。

- **isPresented**：绑定到一个布尔值，用于确定是否显示提示框。当用户按下或点击提示框的某个操作时，系统会将此值设置为 `false` 并关闭提示框。

- **actions**：返回警报操作的 [ViewBuilder](../ViewBuilder.zh-Hans.md)。

## 讨论

在下面的示例中，登录表单通过设置 `didFail` 状态变量来有条件地显示警报。当表单将该值设置为 `true` 时，系统会显示一个带有“确定”操作的警报。

```swift
struct Login: View {
    @State private var didFail = false
    let alertTitle: String = "Login failed."

    var body: some View {
        LoginForm(didFail: $didFail)
            .alert(
                Text(alertTitle),
                isPresented: $didFail
            ) {
                Button("OK") {
                    // Handle the acknowledgement.
                }
            }
    }
}
```

警报中的所有操作都会在执行完毕后关闭警报。默认按钮会以更高的优先级显示。您可以通过为默认按钮分配 [defaultAction](../KeyboardShortcut/defaultAction.zh-Hans.md) 键盘快捷键来控制其优先级。

系统可能会根据按钮的作用和优先级重新排列按钮的顺序。

如果没有指定任何操作，系统会包含一个标准的“确定”操作。系统不提供默认的取消操作。如果要显示取消操作，请使用角色为 [cancel](../ButtonRole/cancel.zh-Hans.md) 的按钮。

在 iOS、tvOS 和 watchOS 上，提示框仅支持标签为 [Text](../Text.zh-Hans.md) 的控件。传递任何其他类型的视图都会导致内容被省略。

## 显示提示框

- **AlertScene**：一个将自身渲染为独立提示框的场景。

- **alert(_:isPresented:presenting:actions:)**：使用给定数据生成提示框内容，并以文本视图作为标题。

- **alert(isPresented:error:actions:)**：当出现错误时显示提示框。

- **alert(_:isPresented:actions:message:)**：当给定条件为真时，以文本视图作为标题显示带有消息的提示框。

- **alert(_:isPresented:presenting:actions:message:)**：根据给定数据生成警报内容，并以文本视图显示标题，从而显示警报信息。

- **alert(isPresented:error:actions:message:)**：当出现错误时，显示警报信息。


---
source: https://developer.apple.com/documentation/SwiftUI/View/alert(_:isPresented:actions:)
crawled: 2025-12-02T17:30:24Z
---

# alert(_:isPresented:actions:)

**Instance Method**

Presents an alert when a given condition is true, using a text view for the title.

## Declaration

```swift
nonisolated func alert<A>(_ title: Text, isPresented: Binding<Bool>, @ViewBuilder actions: () -> A) -> some View where A : View

```

## Parameters

- **title**: The title of the alert.
- **isPresented**: A binding to a Boolean value that determines whether to present the alert. When the user presses or taps one of the alert’s actions, the system sets this value to `false` and dismisses.
- **actions**: A [ViewBuilder](../ViewBuilder.zh-Hans.md) returning the alert’s actions.

## Discussion

In the example below, a login form conditionally presents an alert by setting the `didFail` state variable. When the form sets the value to to `true`, the system displays an alert with an “OK” action.

```swift
struct Login: View {
    @State private var didFail = false
    let alertTitle: String = "Login failed."

    var body: some View {
        LoginForm(didFail: $didFail)
            .alert(
                Text(alertTitle),
                isPresented: $didFail
            ) {
                Button("OK") {
                    // Handle the acknowledgement.
                }
            }
    }
}
```

All actions in an alert dismiss the alert after the action runs. The default button is shown with greater prominence.  You can influence the default button by assigning it the [defaultAction](../KeyboardShortcut/defaultAction.zh-Hans.md) keyboard shortcut.

The system may reorder the buttons based on their role and prominence.

If no actions are present, the system includes a standard “OK” action. No default cancel action is provided. If you want to show a cancel action, use a button with a role of [cancel](../ButtonRole/cancel.zh-Hans.md).

On iOS, tvOS, and watchOS, alerts only support controls with labels that are [Text](../Text.zh-Hans.md). Passing any other type of view results in the content being omitted.

## Presenting an alert

- **AlertScene**: A scene that renders itself as a standalone alert dialog.
- **alert(_:isPresented:presenting:actions:)**: Presents an alert using the given data to produce the alert’s content and a text view as a title.
- **alert(isPresented:error:actions:)**: Presents an alert when an error is present.
- **alert(_:isPresented:actions:message:)**: Presents an alert with a message when a given condition is true using a text view as a title.
- **alert(_:isPresented:presenting:actions:message:)**: Presents an alert with a message using the given data to produce the alert’s content and a text view for a title.
- **alert(isPresented:error:actions:message:)**: Presents an alert with a message when an error is present.

