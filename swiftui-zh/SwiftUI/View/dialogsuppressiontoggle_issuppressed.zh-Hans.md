--- 来源：https://developer.apple.com/documentation/SwiftUI/View/dialogSuppressionToggle(isSuppressed:)

抓取时间：2025-12-02T17:30:40Z

---

# dialogSuppressionToggle(isSuppressed:)

**实例方法**

允许用户屏蔽在 `self` 中显示的对话框和警告，macOS 上会显示默认的屏蔽消息。其他平台未使用。

## 声明

```swift
nonisolated func dialogSuppressionToggle(isSuppressed: Binding<Bool>) -> some View

```

## 参数

- **isSuppressed**：对话框中的屏蔽开关是否开启。

## 说明

在 macOS 上应用对话框屏蔽功能会在对话框中添加一个开关，允许用户请求不再显示该警告。通常情况下，对话框是否被抑制的状态存储在 `AppStorage` 中，并用于决定将来是否显示该对话框。

以下示例配置了一个带有抑制开关的 `confirmationDialog`。该开关的状态存储在 `AppStorage` 中，并用于确定在按下“删除项目”按钮时是否显示对话框。

```swift
struct ConfirmEraseItems: View {
    @State private var isShowingDialog = false

    @AppStorage("suppressEraseItemAlert")
    private var suppressAlert = false

    var body: some View {
        Button("Delete Items") {
            if !suppressAlert {
                isShowingDialog = true
            } else {
                // Handle item deletion.
            }
        }
        .confirmationDialog(
            "Are you sure you want to erase these items?",
            isPresented: $isShowingDialog
        ) {
            Button("Erase", role: .destructive) {
                // Handle item deletion.
            }
            Button("Cancel", role: .cancel) {
                isShowingDialog = false
            }
        }
        .dialogSuppressionToggle(isSuppressed: $suppressAlert)
    }
}
```

## 配置对话框

- **dialogIcon(_:)**：配置此视图中对话框使用的图标。

- **dialogIcon(_:)**：配置警报使用的图标。

- **dialogSeverity(_:)**

- **dialogSeverity(_:)**：设置警报的严重级别。

- **dialogSuppressionToggle(isSuppressed:)**：允许用户使用自定义抑制消息来抑制警报。

- **dialogSuppressionToggle(_:isSuppressed:)**：允许用户使用自定义抑制消息来抑制 macOS 系统上 `self` 中显示的对话框和警报。其他平台未使用此功能。

- **dialogSuppressionToggle(_:isSuppressed:)**：允许用户使用自定义抑制消息来抑制警报。


---
source: https://developer.apple.com/documentation/SwiftUI/View/dialogSuppressionToggle(isSuppressed:)
crawled: 2025-12-02T17:30:40Z
---

# dialogSuppressionToggle(isSuppressed:)

**Instance Method**

Enables user suppression of dialogs and alerts presented within `self`, with a default suppression message on macOS. Unused on other platforms.

## Declaration

```swift
nonisolated func dialogSuppressionToggle(isSuppressed: Binding<Bool>) -> some View

```

## Parameters

- **isSuppressed**: Whether the suppression toggle is on or off in the dialog.

## Discussion

Applying dialog suppression adds a toggle to dialogs on macOS, which allows the user to request the alert not be displayed again. Typically whether a dialog is suppressed is stored in `AppStorage` and used to decide whether to present the dialog in the future.

The following example configures a `confirmationDialog` with a suppression toggle. The toggle’s state is stored in `AppStorage` and used to determine whether or not to show the dialog when the “Delete Items” button is pressed.

```swift
struct ConfirmEraseItems: View {
    @State private var isShowingDialog = false

    @AppStorage("suppressEraseItemAlert")
    private var suppressAlert = false

    var body: some View {
        Button("Delete Items") {
            if !suppressAlert {
                isShowingDialog = true
            } else {
                // Handle item deletion.
            }
        }
        .confirmationDialog(
            "Are you sure you want to erase these items?",
            isPresented: $isShowingDialog
        ) {
            Button("Erase", role: .destructive) {
                // Handle item deletion.
            }
            Button("Cancel", role: .cancel) {
                isShowingDialog = false
            }
        }
        .dialogSuppressionToggle(isSuppressed: $suppressAlert)
    }
}
```

## Configuring a dialog

- **dialogIcon(_:)**: Configures the icon used by dialogs within this view.
- **dialogIcon(_:)**: Configures the icon used by alerts.
- **dialogSeverity(_:)**
- **dialogSeverity(_:)**: Sets the severity for alerts.
- **dialogSuppressionToggle(isSuppressed:)**: Enables user suppression of an alert with a custom suppression message.
- **dialogSuppressionToggle(_:isSuppressed:)**: Enables user suppression of dialogs and alerts presented within `self`, with a custom suppression message on macOS. Unused on other platforms.
- **dialogSuppressionToggle(_:isSuppressed:)**: Enables user suppression of an alert with a custom suppression message.

