--- 来源：https://developer.apple.com/documentation/SwiftUI/View/confirmationDialog(_:isPresented:titleVisibility:presenting:actions:)

抓取时间：2025-12-02T17:30:29Z

---

# confirmationDialog(_:isPresented:titleVisibility:presenting:actions:)

**实例方法**

使用数据生成确认对话框的内容，并使用文本视图显示标题。

## 声明

```swift
nonisolated func confirmationDialog<A, T>(_ title: Text, isPresented: Binding<Bool>, titleVisibility: Visibility = .automatic, presenting data: T?, @ViewBuilder actions: (T) -> A) -> some View where A : View

```

## 参数

- **title**：对话框的标题。

- **isPresented**：绑定到一个布尔值，用于确定是否显示对话框。当用户按下或点击对话框的默认操作按钮时，系统会将此值设置为 `false`，从而关闭对话框。

- **titleVisibility**：对话框标题的可见性。默认值为 [automatic](../Visibility/automatic.zh-Hans.md)。

- **data**：确认对话框的可选数据源。系统会将数据源的内容传递给修饰符的闭包。您可以使用此数据来填充您创建的确认对话框的字段，该对话框将显示给用户。

- **actions**：一个视图构建器，它根据当前可用数据返回对话框的操作。

## 讨论

为了使界面正常显示，`isPresented` 必须为 `true`，且 `data` 不能为 `nil`。`data` 在显示完成后不应更改。显示完成后发生的任何更改都将被忽略。

当您需要使用数据源中的内容填充确认对话框的字段时，请使用此方法。以下示例显示了一个自定义数据源 `FileDetails`，它提供数据来填充对话框：

```swift
struct FileDetails: Identifiable {
    var id: String { name }
    let name: String
    let fileType: UTType
}
struct ConfirmFileImport: View {
    @State private var isConfirming = false
    @State private var dialogDetail: FileDetails?
    var body: some View {
        Button("Import File") {
            dialogDetail = FileDetails(
                name: "MyImageFile.png", fileType: .png)
            isConfirming = true
        }
        .confirmationDialog(
            Text("Import New File?"),
            isPresented: $isConfirming, presenting: dialogDetail
        ) { detail in
            Button {
                // Handle import action.
            } label: {
                Text("""
                Import \(detail.name)
                File Type: \(detail.fileType.description)
                """)
            }
            Button("Cancel", role: .cancel) {
                dialogDetail = nil
            }
        }
    }
}
```

确认对话框中的所有操作都会在操作完成后关闭对话框。默认按钮将以更高的优先级显示。您可以通过为默认按钮分配 [defaultAction](../KeyboardShortcut/defaultAction.zh-Hans.md) 键盘快捷键来控制它。

系统可能会根据按钮的角色和重要性重新排列按钮顺序。

对话框默认包含一个标准的关闭操作。如果您提供一个角色为 [cancel](../ButtonRole/cancel.zh-Hans.md) 的按钮，该按钮将取代默认的关闭操作。您无需使用取消按钮的操作来关闭对话框。

在 iOS、tvOS 和 watchOS 上，确认对话框仅支持标签为 `Text` 的控件。传递任何其他类型的视图都会导致内容被省略。

## 获取操作确认

- **confirmationDialog(_:isPresented:titleVisibility:actions:)**：当给定条件为真时，显示一个确认对话框，标题使用文本视图。

- **dismissalConfirmationDialog(_:shouldPresent:actions:)**：当触发关闭操作时，显示一个确认对话框。


---
source: https://developer.apple.com/documentation/SwiftUI/View/confirmationDialog(_:isPresented:titleVisibility:presenting:actions:)
crawled: 2025-12-02T17:30:29Z
---

# confirmationDialog(_:isPresented:titleVisibility:presenting:actions:)

**Instance Method**

Presents a confirmation dialog using data to produce the dialog’s content and a text view for the title.

## Declaration

```swift
nonisolated func confirmationDialog<A, T>(_ title: Text, isPresented: Binding<Bool>, titleVisibility: Visibility = .automatic, presenting data: T?, @ViewBuilder actions: (T) -> A) -> some View where A : View

```

## Parameters

- **title**: The title of the dialog.
- **isPresented**: A binding to a Boolean value that determines whether to present the dialog. When the user presses or taps the dialog’s default action button, the system sets this value to `false`, dismissing the dialog.
- **titleVisibility**: The visibility of the dialog’s title. The default value is [automatic](../Visibility/automatic.zh-Hans.md).
- **data**: An optional source of truth for the confirmation dialog. The system passes the contents to the modifier’s closures. You use this data to populate the fields of a confirmation dialog that you create that the system displays to the user.
- **actions**: A view builder returning the dialog’s actions given the currently available data.

## Discussion

In order for the interface to appear, both `isPresented` must be `true` and `data` must not be `nil`. `data` should not change after the presentation occurs. Any changes which occur after the presentation occurs will be ignored.

Use this method when you need to populate the fields of a confirmation dialog with content from a data source. The example below shows a custom data source, `FileDetails`, that provides data to populate the dialog:

```swift
struct FileDetails: Identifiable {
    var id: String { name }
    let name: String
    let fileType: UTType
}
struct ConfirmFileImport: View {
    @State private var isConfirming = false
    @State private var dialogDetail: FileDetails?
    var body: some View {
        Button("Import File") {
            dialogDetail = FileDetails(
                name: "MyImageFile.png", fileType: .png)
            isConfirming = true
        }
        .confirmationDialog(
            Text("Import New File?"),
            isPresented: $isConfirming, presenting: dialogDetail
        ) { detail in
            Button {
                // Handle import action.
            } label: {
                Text("""
                Import \(detail.name)
                File Type: \(detail.fileType.description)
                """)
            }
            Button("Cancel", role: .cancel) {
                dialogDetail = nil
            }
        }
    }
}
```

All actions in a confirmation dialog will dismiss the dialog after the action runs. The default button will be shown with greater prominence. You can influence the default button by assigning it the [defaultAction](../KeyboardShortcut/defaultAction.zh-Hans.md) keyboard shortcut.

The system may reorder the buttons based on their role and prominence.

Dialogs include a standard dismiss action by default. If you provide a button with a role of [cancel](../ButtonRole/cancel.zh-Hans.md), that button takes the place of the default dismiss action. You don’t have to dismiss the presentation with the cancel button’s action.



On iOS, tvOS, and watchOS, confirmation dialogs only support controls with labels that are `Text`. Passing any other type of view results in the content being omitted.

## Getting confirmation for an action

- **confirmationDialog(_:isPresented:titleVisibility:actions:)**: Presents a confirmation dialog when a given condition is true, using a text view for the title.
- **dismissalConfirmationDialog(_:shouldPresent:actions:)**: Presents a confirmation dialog when a dismiss action has been triggered.

