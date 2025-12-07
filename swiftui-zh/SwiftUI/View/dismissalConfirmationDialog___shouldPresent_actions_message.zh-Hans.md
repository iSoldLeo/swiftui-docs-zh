--- 来源：https://developer.apple.com/documentation/SwiftUI/View/dismissalConfirmationDialog(_:shouldPresent:actions:message:)

抓取时间：2025-12-02T17:30:31Z

---

# dismissalConfirmationDialog(_:shouldPresent:actions:message:)

**实例方法**

当触发关闭操作时，显示确认对话框。

## 声明

```swift
nonisolated func dismissalConfirmationDialog<A, M>(_ title: Text, shouldPresent: Bool, @ViewBuilder actions: () -> A, @ViewBuilder message: () -> M) -> some View where A : View, M : View

```

## 参数

- **title**：对话框标题。

- **shouldPresent**：一个布尔值，用于确定关闭操作时是否显示对话框。

- **actions**：一个返回对话框操作的视图构建器。

- **message**：返回对话框消息的视图构建器。

## 讨论

在 macOS 上，尝试关闭此视图窗口时会显示对话框。

例如，您可以显示一个对话框，询问是否保存未保存的更改：

struct ComposeMessage: View { @State private var message = Message()

```swift
var body: some View {
    MessageEditor(message: $message)
        .dismissalConfirmationDialog(
            "Save This Message As Draft?",
            shouldPresent: message.hasUnsavedChanges
        ) {
            Button("Save") {
                message.save()
            }
            Button("Don't Save", role: .destructive) {
                message.discard()
            }
        } message: {
            Text(
                """
                This message has not been sent and contains\
                unsaved changes.
                """)
        }
```

}

对话框中的所有操作都会在操作完成后关闭对话框。默认按钮将以更高的优先级显示。您可以通过为其分配 [defaultAction](../KeyboardShortcut/defaultAction.zh-Hans.md) 快捷键来影响默认按钮。

系统可能会根据按钮的角色和优先级重新排列按钮顺序。

默认情况下，关闭对话框包含一个标准的取消操作。如果您提供一个角色为 [cancel](../ButtonRole/cancel.zh-Hans.md) 的按钮，则该按钮将取代默认的取消操作。

取消操作始终会阻止解雇，而其他操作则允许解雇继续进行。

## 显示带有消息的确认对话框

- **confirmationDialog(_:isPresented:titleVisibility:actions:message:)**：当满足给定条件时，显示带有消息的确认对话框，标题使用文本视图。

- **confirmationDialog(_:isPresented:titleVisibility:presenting:actions:message:)**：显示带有消息的确认对话框，对话框内容由数据生成，消息使用文本视图。


---
source: https://developer.apple.com/documentation/SwiftUI/View/dismissalConfirmationDialog(_:shouldPresent:actions:message:)
crawled: 2025-12-02T17:30:31Z
---

# dismissalConfirmationDialog(_:shouldPresent:actions:message:)

**Instance Method**

Presents a confirmation dialog when a dismiss action has been triggered.

## Declaration

```swift
nonisolated func dismissalConfirmationDialog<A, M>(_ title: Text, shouldPresent: Bool, @ViewBuilder actions: () -> A, @ViewBuilder message: () -> M) -> some View where A : View, M : View

```

## Parameters

- **title**: The title of the dialog.
- **shouldPresent**: A Boolean value that determines whether to present the dialog upon dismissal.
- **actions**: A view builder returning the dialog’s actions.
- **message**: A view builder returning the message for the dialog.

## Discussion

On macOS, the dialog will be presented when attempting to dismiss the window for this view.

For example, you could present a dialog asking to persist unsaved changes:

struct ComposeMessage: View { @State private var message = Message()

```swift
var body: some View {
    MessageEditor(message: $message)
        .dismissalConfirmationDialog(
            "Save This Message As Draft?",
            shouldPresent: message.hasUnsavedChanges
        ) {
            Button("Save") {
                message.save()
            }
            Button("Don't Save", role: .destructive) {
                message.discard()
            }
        } message: {
            Text(
                """
                This message has not been sent and contains\
                unsaved changes.
                """)
        }
```

}

All actions in the dialog will dismiss the dialog after the action runs. The default button will be shown with greater prominence. You can influence the default button by assigning it the [defaultAction](../KeyboardShortcut/defaultAction.zh-Hans.md) keyboard shortcut.

The system may reorder the buttons based on their role and prominence.

Dismissal dialogs include a standard cancellation action by default. If you provide a button with a role of [cancel](../ButtonRole/cancel.zh-Hans.md), that button takes the place of the default cancellation action.

The cancellation action will always prevent the dismissal, while other actions will allow the dismiss to proceed.

## Showing a confirmation dialog with a message

- **confirmationDialog(_:isPresented:titleVisibility:actions:message:)**: Presents a confirmation dialog with a message when a given condition is true, using a text view for the title.
- **confirmationDialog(_:isPresented:titleVisibility:presenting:actions:message:)**: Presents a confirmation dialog with a message using data to produce the dialog’s content and a text view for the message.

