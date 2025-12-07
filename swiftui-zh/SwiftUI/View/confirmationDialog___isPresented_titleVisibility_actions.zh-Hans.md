--- 来源：https://developer.apple.com/documentation/SwiftUI/View/confirmationDialog(_:isPresented:titleVisibility:actions:)

抓取时间：2025-12-02T17:30:28Z

---

# confirmationDialog(_:isPresented:titleVisibility:actions:)

**实例方法**

当给定条件为真时，显示一个确认对话框，标题使用文本视图。

## 声明

```swift
nonisolated func confirmationDialog<A>(_ title: Text, isPresented: Binding<Bool>, titleVisibility: Visibility = .automatic, @ViewBuilder actions: () -> A) -> some View where A : View

```

## 参数

- **title**：对话框的标题。

- **isPresented**：绑定到一个布尔值，用于确定是否显示对话框。当用户按下或点击对话框的默认操作按钮时，系统会将此值设置为 `false`，从而关闭对话框。

- **titleVisibility**：对话框标题的可见性。默认值为 [automatic](../Visibility/automatic.zh-Hans.md)。

- **actions**：返回对话框操作的视图构建器。

## 讨论

在下面的示例中，按钮会根据绑定布尔变量的值有条件地显示确认对话框。当布尔值设置为 `true` 时，系统会显示一个包含取消操作和删除操作的确认对话框。

```swift
struct ConfirmEraseItems: View {
    @State private var isShowingDialog = false
    var body: some View {
        Button("Empty Trash") {
            isShowingDialog = true
        }
        .confirmationDialog(
            Text("Permanently erase the items in the trash?"),
            isPresented: $isShowingDialog
        ) {
            Button("Empty Trash", role: .destructive) {
                // Handle empty trash action.
            }
        }
    }
}
```

确认对话框中的所有操作都会在执行完毕后关闭对话框。默认按钮将以更醒目的方式显示。您可以通过为默认按钮分配快捷键 [defaultAction](../KeyboardShortcut/defaultAction.zh-Hans.md) 来影响其默认行为。

系统可能会根据按钮的角色和重要性重新排列按钮顺序。

对话框默认包含一个标准的关闭操作。如果您提供一个角色为 [cancel](../ButtonRole/cancel.zh-Hans.md) 的按钮，该按钮将取代默认的关闭操作。您不必使用取消按钮的操作来关闭对话框。

## 获取操作确认

- **confirmationDialog(_:isPresented:titleVisibility:presenting:actions:)**：使用数据生成对话框内容和标题文本视图，并显示确认对话框。

- **dismissalConfirmationDialog(_:shouldPresent:actions:)**：在触发关闭操作时显示确认对话框。


---
source: https://developer.apple.com/documentation/SwiftUI/View/confirmationDialog(_:isPresented:titleVisibility:actions:)
crawled: 2025-12-02T17:30:28Z
---

# confirmationDialog(_:isPresented:titleVisibility:actions:)

**Instance Method**

Presents a confirmation dialog when a given condition is true, using a text view for the title.

## Declaration

```swift
nonisolated func confirmationDialog<A>(_ title: Text, isPresented: Binding<Bool>, titleVisibility: Visibility = .automatic, @ViewBuilder actions: () -> A) -> some View where A : View

```

## Parameters

- **title**: The title of the dialog.
- **isPresented**: A binding to a Boolean value that determines whether to present the dialog. When the user presses or taps the dialog’s default action button, the system sets this value to `false`, dismissing the dialog.
- **titleVisibility**: The visibility of the dialog’s title. The default value is [automatic](../Visibility/automatic.zh-Hans.md).
- **actions**: A view builder returning the dialog’s actions.

## Discussion

In the example below, a button conditionally presents a confirmation dialog depending upon the value of a bound Boolean variable. When the Boolean value is set to `true`, the system displays a confirmation dialog with a cancel action and a destructive action.

```swift
struct ConfirmEraseItems: View {
    @State private var isShowingDialog = false
    var body: some View {
        Button("Empty Trash") {
            isShowingDialog = true
        }
        .confirmationDialog(
            Text("Permanently erase the items in the trash?"),
            isPresented: $isShowingDialog
        ) {
            Button("Empty Trash", role: .destructive) {
                // Handle empty trash action.
            }
        }
    }
}
```

All actions in a confirmation dialog will dismiss the dialog after the action runs. The default button will be shown with greater prominence. You can influence the default button by assigning it the [defaultAction](../KeyboardShortcut/defaultAction.zh-Hans.md) keyboard shortcut.

The system may reorder the buttons based on their role and prominence.

Dialogs include a standard dismiss action by default. If you provide a button with a role of [cancel](../ButtonRole/cancel.zh-Hans.md), that button takes the place of the default dismiss action. You don’t have to dismiss the presentation with the cancel button’s action.



## Getting confirmation for an action

- **confirmationDialog(_:isPresented:titleVisibility:presenting:actions:)**: Presents a confirmation dialog using data to produce the dialog’s content and a text view for the title.
- **dismissalConfirmationDialog(_:shouldPresent:actions:)**: Presents a confirmation dialog when a dismiss action has been triggered.

