--- 来源：https://developer.apple.com/documentation/SwiftUI/View/alert(_:isPresented:presenting:actions:message:)

抓取时间：2025-11-30T21:15:26Z

---

# alert(_:isPresented:presenting:actions:message:)

**实例方法**

使用给定的数据生成提示框内容，并显示一个文本视图作为标题，从而显示一个带有消息的提示框。

## 声明

```swift
nonisolated func alert<A, M, T>(_ title: Text, isPresented: Binding<Bool>, presenting data: T?, @ViewBuilder actions: (T) -> A, @ViewBuilder message: (T) -> M) -> some View where A : View, M : View

```

## 参数

- **title**：提示框的标题。

- **isPresented**：绑定到一个布尔值，用于确定是否显示提示框。当用户按下或点击警报的某个操作时，系统会将此值设置为 `false` 并关闭警报。

- **data**：警报的可选数据源。系统会将数据源的内容传递给修饰符的闭包。您可以使用此数据来填充您创建的警报的各个字段，以便系统向用户显示该警报。

- **actions**：返回警报操作的 [ViewBuilder](../ViewBuilder.zh-Hans.md) 函数，该函数根据当前可用数据返回警报操作。

- **message**：返回警报消息的 [ViewBuilder](../ViewBuilder.zh-Hans.md) 函数，该函数根据当前可用数据返回警报消息。

## 讨论

要显示此警报，`isPresented` 必须为 `true`，且 `data` 不能为 `nil`。显示后数据不应更改。显示后所做的任何更改都将被忽略。

当您需要使用数据源中的内容填充警报字段时，请使用此方法。以下示例显示了一个自定义数据源 `SaveDetails`，它提供数据来填充警报：

```swift
struct SaveDetails: Identifiable {
    let name: String
    let error: String
    let id = UUID()
}

struct SaveButton: View {
    @State private var didError = false
    @State private var details: SaveDetails?
    let alertTitle: String = "Save failed."

    var body: some View {
        Button("Save") {
            details = model.save(didError: $didError)
        }
        .alert(
            Text(alertTitle),
            isPresented: $didError,
            presenting: details
        ) { details in
            Button(role: .destructive) {
                // Handle the deletion.
            } label: {
                Text("Delete \(details.name)")
            }
            Button("Retry") {
                // Handle the retry action.
            }
        } message: { details in
            Text(details.error)
        }
    }
}
```

警报中的所有操作都会在操作完成后关闭警报。默认按钮会以更高的优先级显示。您可以通过为默认按钮分配快捷键 [defaultAction](../KeyboardShortcut/defaultAction.zh-Hans.md) 来影响其优先级。

系统可能会根据按钮的作用和优先级重新排列按钮的顺序。

如果没有指定任何操作，系统将包含一个标准的“确定”操作。系统不提供默认的取消操作。如果您想要显示取消操作，请使用角色为 [cancel](../ButtonRole/cancel.zh-Hans.md) 的按钮。

在 iOS、tvOS 和 watchOS 上，提示框仅支持标签为 [Text](../Text.zh-Hans.md) 的控件。传递任何其他类型的视图都会导致内容被省略。

消息仅支持无样式文本。

## 显示提示框

- **AlertScene**：一个将自身渲染为独立提示框对话框的场景。

- **alert(_:isPresented:actions:)**：当给定条件为真时显示提示框，并使用文本视图作为标题。

- **alert(_:isPresented:presenting:actions:)**：使用给定数据生成提示框内容，并使用文本视图作为标题。

- **alert(isPresented:error:actions:)**：出现错误时显示警报。

- **alert(_:isPresented:actions:message:)**：当满足给定条件时，显示带有消息的警报，并以文本视图作为标题。

- **alert(isPresented:error:actions:message:)**：出现错误时显示带有消息的警报。


---
source: https://developer.apple.com/documentation/SwiftUI/View/alert(_:isPresented:presenting:actions:message:)
crawled: 2025-11-30T21:15:26Z
---

# alert(_:isPresented:presenting:actions:message:)

**Instance Method**

Presents an alert with a message using the given data to produce the alert’s content and a text view for a title.

## Declaration

```swift
nonisolated func alert<A, M, T>(_ title: Text, isPresented: Binding<Bool>, presenting data: T?, @ViewBuilder actions: (T) -> A, @ViewBuilder message: (T) -> M) -> some View where A : View, M : View

```

## Parameters

- **title**: The title of the alert.
- **isPresented**: A binding to a Boolean value that determines whether to present the alert. When the user presses or taps one of the alert’s actions, the system sets this value to `false` and dismisses.
- **data**: An optional source of truth for the alert. The system passes the contents to the modifier’s closures. You use this data to populate the fields of an alert that you create that the system displays to the user.
- **actions**: A [ViewBuilder](../ViewBuilder.zh-Hans.md) returning the alert’s actions given the currently available data.
- **message**: A [ViewBuilder](../ViewBuilder.zh-Hans.md) returning the message for the alert given the currently available data.

## Discussion

For the alert to appear, both `isPresented` must be `true` and `data` must not be `nil`. The data should not change after the presentation occurs. Any changes that you make after the presentation occurs are ignored.

Use this method when you need to populate the fields of an alert with content from a data source. The example below shows a custom data source, `SaveDetails`, that provides data to populate the alert:

```swift
struct SaveDetails: Identifiable {
    let name: String
    let error: String
    let id = UUID()
}

struct SaveButton: View {
    @State private var didError = false
    @State private var details: SaveDetails?
    let alertTitle: String = "Save failed."

    var body: some View {
        Button("Save") {
            details = model.save(didError: $didError)
        }
        .alert(
            Text(alertTitle),
            isPresented: $didError,
            presenting: details
        ) { details in
            Button(role: .destructive) {
                // Handle the deletion.
            } label: {
                Text("Delete \(details.name)")
            }
            Button("Retry") {
                // Handle the retry action.
            }
        } message: { details in
            Text(details.error)
        }
    }
}
```

All actions in an alert dismiss the alert after the action runs. The default button is shown with greater prominence.  You can influence the default button by assigning it the [defaultAction](../KeyboardShortcut/defaultAction.zh-Hans.md) keyboard shortcut.

The system may reorder the buttons based on their role and prominence.

If no actions are present, the system includes a standard “OK” action. No default cancel action is provided. If you want to show a cancel action, use a button with a role of [cancel](../ButtonRole/cancel.zh-Hans.md).

On iOS, tvOS, and watchOS, alerts only support controls with labels that are [Text](../Text.zh-Hans.md). Passing any other type of view results in the content being omitted.

Only unstyled text is supported for the message.

## Presenting an alert

- **AlertScene**: A scene that renders itself as a standalone alert dialog.
- **alert(_:isPresented:actions:)**: Presents an alert when a given condition is true, using a text view for the title.
- **alert(_:isPresented:presenting:actions:)**: Presents an alert using the given data to produce the alert’s content and a text view as a title.
- **alert(isPresented:error:actions:)**: Presents an alert when an error is present.
- **alert(_:isPresented:actions:message:)**: Presents an alert with a message when a given condition is true using a text view as a title.
- **alert(isPresented:error:actions:message:)**: Presents an alert with a message when an error is present.

