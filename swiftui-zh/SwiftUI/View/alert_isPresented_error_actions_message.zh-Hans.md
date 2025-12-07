--- 来源：https://developer.apple.com/documentation/SwiftUI/View/alert(isPresented:error:actions:message:)

抓取时间：2025-11-30T21:15:27Z

---

# alert(isPresented:error:actions:message:)

**实例方法**

当出现错误时，显示一个带有错误信息的提示框。

## 声明

```swift
nonisolated func alert<E, A, M>(isPresented: Binding<Bool>, error: E?, @ViewBuilder actions: (E) -> A, @ViewBuilder message: (E) -> M) -> some View where E : LocalizedError, A : View, M : View

```

## 参数

- **isPresented**：绑定到一个布尔值，用于确定是否显示提示框。当用户按下或点击提示框的某个操作时，系统会将此值设置为 `false` 并关闭提示框。

- **error**：一个可选的本地化错误，用于生成提示框的标题。系统会将内容传递给修饰符的闭包。您可以使用此数据填充您创建的警报的字段，该警报将显示给用户。

- **actions**：返回警报操作的 [ViewBuilder](../ViewBuilder.zh-Hans.md)。

- **message**：根据当前错误返回警报消息的视图构建器。

## 讨论

在下面的示例中，表单会根据错误的值有条件地显示警报。当错误值不是 `nil` 时，系统会显示一个带有“确定”操作的警报。

警报的标题从错误的 `errorDescription` 推断得出。

```swift
struct TicketPurchase: View {
    @State private var error: TicketPurchaseError? = nil
    @State private var showAlert = false

    var body: some View {
        TicketForm(showAlert: $showAlert, error: $error)
            .alert(isPresented: $showAlert, error: error) { _ in
                Button("OK") {
                    // Handle acknowledgement.
                }
            } message: { error in
                Text(error.recoverySuggestion ?? "Try again later.")
            }
    }
}
```

警报中的所有操作都会在执行完毕后关闭警报。默认按钮会以更醒目的方式显示。您可以通过为默认按钮分配快捷键 [defaultAction](../KeyboardShortcut/defaultAction.zh-Hans.md) 来影响其显示。

系统可能会根据按钮的角色和重要性重新排列按钮顺序。

如果没有指定任何操作，系统会默认显示“确定”操作。系统不提供默认的取消操作。如果您想要显示取消操作，请使用角色为 [cancel](../ButtonRole/cancel.zh-Hans.md) 的按钮。

在 iOS、tvOS 和 watchOS 上，提示框仅支持标签为 [Text](../Text.zh-Hans.md) 的控件。传递任何其他类型的视图都会导致内容被省略。

此修饰符会为您创建一个标题的 [Text](../Text.zh-Hans.md) 视图，并将本地化键的处理方式与 [init(_:tableName:bundle:comment:)](../Text/init___tableName_bundle_comment.zh-Hans.md) 类似。有关字符串本地化的更多信息，请参阅 [Text](../Text.zh-Hans.md)。

## 显示警告

- **AlertScene**：一个可独立渲染为警告对话框的场景。

- **alert(_:isPresented:actions:)**：当满足给定条件时显示警告，标题使用文本视图。

- **alert(_:isPresented:presenting:actions:)**：使用给定数据生成警告内容，并使用文本视图作为标题。

- **alert(isPresented:error:actions:)**：当出现错误时显示警告。

- **alert(_:isPresented:actions:message:)**：当满足给定条件时显示带有消息的警告，标题使用文本视图。

- **alert(_:isPresented:presenting:actions:message:)**：使用给定数据生成警告内容，并使用文本视图作为标题，显示带有消息的警告。


---
source: https://developer.apple.com/documentation/SwiftUI/View/alert(isPresented:error:actions:message:)
crawled: 2025-11-30T21:15:27Z
---

# alert(isPresented:error:actions:message:)

**Instance Method**

Presents an alert with a message when an error is present.

## Declaration

```swift
nonisolated func alert<E, A, M>(isPresented: Binding<Bool>, error: E?, @ViewBuilder actions: (E) -> A, @ViewBuilder message: (E) -> M) -> some View where E : LocalizedError, A : View, M : View

```

## Parameters

- **isPresented**: A binding to a Boolean value that determines whether to present the alert. When the user presses or taps one of the alert’s actions, the system sets this value to `false` and dismisses.
- **error**: An optional localized Error that is used to generate the alert’s title.  The system passes the contents to the modifier’s closures. You use this data to populate the fields of an alert that you create that the system displays to the user.
- **actions**: A [ViewBuilder](../ViewBuilder.zh-Hans.md) returning the alert’s actions.
- **message**: A view builder returning the message for the alert given the current error.

## Discussion

In the example below, a form conditionally presents an alert depending upon the value of an error. When the error value isn’t `nil`, the system presents an alert with an “OK” action.

The title of the alert is inferred from the error’s `errorDescription`.

```swift
struct TicketPurchase: View {
    @State private var error: TicketPurchaseError? = nil
    @State private var showAlert = false

    var body: some View {
        TicketForm(showAlert: $showAlert, error: $error)
            .alert(isPresented: $showAlert, error: error) { _ in
                Button("OK") {
                    // Handle acknowledgement.
                }
            } message: { error in
                Text(error.recoverySuggestion ?? "Try again later.")
            }
    }
}
```

All actions in an alert dismiss the alert after the action runs. The default button is shown with greater prominence.  You can influence the default button by assigning it the [defaultAction](../KeyboardShortcut/defaultAction.zh-Hans.md) keyboard shortcut.

The system may reorder the buttons based on their role and prominence.

If no actions are present, the system includes a standard “OK” action. No default cancel action is provided. If you want to show a cancel action, use a button with a role of [cancel](../ButtonRole/cancel.zh-Hans.md).

On iOS, tvOS, and watchOS, alerts only support controls with labels that are [Text](../Text.zh-Hans.md). Passing any other type of view results in the content being omitted.

This modifier creates a [Text](../Text.zh-Hans.md) view for the title on your behalf, and treats the localized key similar to [init(_:tableName:bundle:comment:)](../Text/init___tableName_bundle_comment.zh-Hans.md). See [Text](../Text.zh-Hans.md) for more information about localizing strings.

## Presenting an alert

- **AlertScene**: A scene that renders itself as a standalone alert dialog.
- **alert(_:isPresented:actions:)**: Presents an alert when a given condition is true, using a text view for the title.
- **alert(_:isPresented:presenting:actions:)**: Presents an alert using the given data to produce the alert’s content and a text view as a title.
- **alert(isPresented:error:actions:)**: Presents an alert when an error is present.
- **alert(_:isPresented:actions:message:)**: Presents an alert with a message when a given condition is true using a text view as a title.
- **alert(_:isPresented:presenting:actions:message:)**: Presents an alert with a message using the given data to produce the alert’s content and a text view for a title.

