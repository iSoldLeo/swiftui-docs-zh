--- 来源：https://developer.apple.com/documentation/SwiftUI/View/alert(_:isPresented:presenting:actions:)

抓取时间：2025-11-30T21:15:24Z

---

# alert(_:isPresented:presenting:actions:)

**实例方法**

使用给定的数据生成提示框内容，并以文本视图作为标题。

## 声明

```swift
nonisolated func alert<A, T>(_ title: Text, isPresented: Binding<Bool>, presenting data: T?, @ViewBuilder actions: (T) -> A) -> some View where A : View

```

## 参数

- **title**：提示框的标题。

- **isPresented**：绑定到一个布尔值，用于确定是否显示提示框。当用户按下或点击提示框的某个操作时，系统会将此值设置为 `false` 并关闭提示框。

- **data**：警报的可选数据源。系统会将数据源内容传递给修改器的闭包。您可以使用此数据填充您创建的警报字段，系统会将该警报显示给用户。

- **actions**：一个 [ViewBuilder](../ViewBuilder.zh-Hans.md)，根据当前可用数据返回警报的操作。

## 讨论

要使警报显示，`isPresented` 必须为 `true`，且 `data` 不能为 `nil`。显示后数据不应更改。显示后所做的任何更改都将被忽略。

当您需要使用数据源中的内容填充警报字段时，请使用此方法。以下示例展示了一个自定义数据源 `SaveDetails`，它提供数据来填充警报：

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
        }
    }
}
```

警报中的所有操作都会在执行完毕后关闭警报。默认按钮会以更高的优先级显示。您可以通过为其分配 [defaultAction](../KeyboardShortcut/defaultAction.zh-Hans.md) 键盘快捷键来控制默认按钮。

系统可能会根据按钮的角色和优先级重新排列按钮顺序。

如果没有指定任何操作，系统会包含一个标准的“确定”操作。系统不提供默认的取消操作。如果您想要显示取消操作，请使用角色为 [cancel](../ButtonRole/cancel.zh-Hans.md) 的按钮。

在 iOS、tvOS 和 watchOS 上，警报仅支持标签为 [Text](../Text.zh-Hans.md) 的控件。传递任何其他类型的视图都会导致内容被省略。

## 显示警告

- **AlertScene**：一个将自身渲染为独立警告对话框的场景。

- **alert(_:isPresented:actions:)**：当给定条件为真时显示警告，标题使用文本视图。

- **alert(isPresented:error:actions:)**：当出现错误时显示警告。

- **alert(_:isPresented:actions:message:)**：当给定条件为真时显示带有消息的警告，标题使用文本视图。

- **alert(_:isPresented:presenting:actions:message:)**：使用给定数据生成警告内容，并使用文本视图作为标题，显示带有消息的警告。

- **alert(isPresented:error:actions:message:)**：当出现错误时显示带有消息的警告。


---
source: https://developer.apple.com/documentation/SwiftUI/View/alert(_:isPresented:presenting:actions:)
crawled: 2025-11-30T21:15:24Z
---

# alert(_:isPresented:presenting:actions:)

**Instance Method**

Presents an alert using the given data to produce the alert’s content and a text view as a title.

## Declaration

```swift
nonisolated func alert<A, T>(_ title: Text, isPresented: Binding<Bool>, presenting data: T?, @ViewBuilder actions: (T) -> A) -> some View where A : View

```

## Parameters

- **title**: The title of the alert.
- **isPresented**: A binding to a Boolean value that determines whether to present the alert. When the user presses or taps one of the alert’s actions, the system sets this value to `false` and dismisses.
- **data**: An optional source of truth for the alert. The system passes the contents to the modifier’s closures. You use this data to populate the fields of an alert that you create that the system displays to the user.
- **actions**: A [ViewBuilder](../ViewBuilder.zh-Hans.md) returning the alert’s actions given the currently available data.

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
- **alert(_:isPresented:actions:)**: Presents an alert when a given condition is true, using a text view for the title.
- **alert(isPresented:error:actions:)**: Presents an alert when an error is present.
- **alert(_:isPresented:actions:message:)**: Presents an alert with a message when a given condition is true using a text view as a title.
- **alert(_:isPresented:presenting:actions:message:)**: Presents an alert with a message using the given data to produce the alert’s content and a text view for a title.
- **alert(isPresented:error:actions:message:)**: Presents an alert with a message when an error is present.

