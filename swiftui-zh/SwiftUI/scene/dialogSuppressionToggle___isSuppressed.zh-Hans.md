--- 来源：https://developer.apple.com/documentation/swiftui/scene/dialogsuppressiontoggle(_:issuppressed:)

抓取时间：2025-12-03T06:02:49Z

---

# dialogSuppressionToggle(_:isSuppressed:)

**实例方法**

允许用户使用自定义抑制消息来抑制提示框。

## 声明

```swift
nonisolated func dialogSuppressionToggle(_ label: Text, isSuppressed: Binding<Bool>) -> some Scene

```

## 参数

- **label**：对话框中抑制开关的标签。可以省略此参数以使用默认抑制标题。

- **isSuppressed**：对话框中抑制开关的开启或关闭状态。

## 讨论

在 macOS 系统中，启用对话框抑制功能会在对话框上添加一个开关，允许用户选择不再显示该提示。通常，对话框是否被抑制的信息存储在 `AppStorage` 中，并用于决定将来是否显示该对话框。

以下示例配置了一个带有抑制开关的提示。该开关的状态存储在 `AppStorage` 中，并用于确定在按下“删除项目”按钮时是否显示该对话框。

```swift
struct MyApp: App {
    @State private var isShowingDialog = false
    @AppStorage("suppressEraseItemAlert")
    private var suppressAlert = false

    var body: some Scene {
        Window(...) {
            Button("Delete items") {
                isShowingDialog = true
            }
        }

        AlertScene(
            "Are you sure you want to erase these items?",
            isPresented: $isShowingDialog
        ) {
            Button("Erase", role: .destructive) {
                // Handle item deletion.
            }
            Button("Cancel", role: .cancel) {
                // Handle cancellation
            }
        }
        .dialogSuppressionToggle(
            "Do not ask about erasing items again",
            isSuppressed: $suppressAlert)
    }
}
```

## 配置对话框

- **dialogIcon(_:)**：配置此视图中对话框使用的图标。

- **dialogIcon(_:)**：配置提示使用的图标。

- **dialogSeverity(_:)**

- **dialogSeverity(_:)**：设置警报的严重级别。

- **dialogSuppressionToggle(isSuppressed:)**：允许用户屏蔽 `self` 中显示的对话框和警报，macOS 系统上会显示默认的屏蔽消息。其他平台未使用此功能。

- **dialogSuppressionToggle(isSuppressed:)**：允许用户屏蔽警报，并可使用自定义的屏蔽消息。

- **dialogSuppressionToggle(_:isSuppressed:)**：允许用户屏蔽 `self` 中显示的对话框和警报，macOS 系统上会显示自定义的屏蔽消息。其他平台未使用此功能。


---
source: https://developer.apple.com/documentation/swiftui/scene/dialogsuppressiontoggle(_:issuppressed:)
crawled: 2025-12-03T06:02:49Z
---

# dialogSuppressionToggle(_:isSuppressed:)

**Instance Method**

Enables user suppression of an alert with a custom suppression message.

## Declaration

```swift
nonisolated func dialogSuppressionToggle(_ label: Text, isSuppressed: Binding<Bool>) -> some Scene

```

## Parameters

- **label**: The label of the suppression toggle in the dialog. This parameter can be elided to use the default suppression title.
- **isSuppressed**: Whether the suppression toggle is on or off in the dialog.

## Discussion

Applying dialog suppression adds a toggle to dialogs on macOS, which allows the user to request the alert not be displayed again. Typically whether a dialog is suppressed is stored in `AppStorage` and used to decide whether to present the dialog in the future.

The following example configures an alert with a suppression toggle. The toggle’s state is stored in `AppStorage` and used to determine whether or not to show the dialog when the “Delete Items” button is pressed.

```swift
struct MyApp: App {
    @State private var isShowingDialog = false
    @AppStorage("suppressEraseItemAlert")
    private var suppressAlert = false

    var body: some Scene {
        Window(...) {
            Button("Delete items") {
                isShowingDialog = true
            }
        }

        AlertScene(
            "Are you sure you want to erase these items?",
            isPresented: $isShowingDialog
        ) {
            Button("Erase", role: .destructive) {
                // Handle item deletion.
            }
            Button("Cancel", role: .cancel) {
                // Handle cancellation
            }
        }
        .dialogSuppressionToggle(
            "Do not ask about erasing items again",
            isSuppressed: $suppressAlert)
    }
}
```

## Configuring a dialog

- **dialogIcon(_:)**: Configures the icon used by dialogs within this view.
- **dialogIcon(_:)**: Configures the icon used by alerts.
- **dialogSeverity(_:)**
- **dialogSeverity(_:)**: Sets the severity for alerts.
- **dialogSuppressionToggle(isSuppressed:)**: Enables user suppression of dialogs and alerts presented within `self`, with a default suppression message on macOS. Unused on other platforms.
- **dialogSuppressionToggle(isSuppressed:)**: Enables user suppression of an alert with a custom suppression message.
- **dialogSuppressionToggle(_:isSuppressed:)**: Enables user suppression of dialogs and alerts presented within `self`, with a custom suppression message on macOS. Unused on other platforms.

