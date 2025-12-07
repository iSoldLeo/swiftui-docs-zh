--- 来源：https://developer.apple.com/documentation/SwiftUI/Scene/dialogSuppressionToggle(isSuppressed:)

抓取时间：2025-12-02T17:30:41Z

---

# dialogSuppressionToggle(isSuppressed:)

**实例方法**

允许用户使用自定义的抑制消息来抑制提示框。

## 声明

```swift
nonisolated func dialogSuppressionToggle(isSuppressed: Binding<Bool>) -> some Scene

```

## 参数

- **isSuppressed**：对话框中抑制开关的开启或关闭状态。

## 说明

在 macOS 上，启用对话框抑制功能会在对话框中添加一个开关，允许用户请求不再显示提示框。通常，对话框是否被抑制的状态存储在 `AppStorage` 中，并用于决定将来是否显示该对话框。

以下示例配置了一个带有抑制开关的警报。该开关的状态存储在 `AppStorage` 中，用于确定在按下“删除项目”按钮时是否显示对话框。

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

- **dialogIcon(_:)**：配置警报使用的图标。

- **dialogSeverity(_:)**

- **dialogSeverity(_:)**：设置警报的严重级别。

- **dialogSuppressionToggle(isSuppressed:)**：启用用户抑制 `self` 中显示的对话框和警报的功能，macOS 上会显示默认的抑制消息。其他平台未使用此功能。

- **dialogSuppressionToggle(_:isSuppressed:)**：允许用户在 macOS 系统上使用自定义屏蔽消息来屏蔽 `self` 中显示的对话框和警报。其他平台未使用此功能。

- **dialogSuppressionToggle(_:isSuppressed:)**：允许用户使用自定义屏蔽消息来屏蔽警报。


---
source: https://developer.apple.com/documentation/SwiftUI/Scene/dialogSuppressionToggle(isSuppressed:)
crawled: 2025-12-02T17:30:41Z
---

# dialogSuppressionToggle(isSuppressed:)

**Instance Method**

Enables user suppression of an alert with a custom suppression message.

## Declaration

```swift
nonisolated func dialogSuppressionToggle(isSuppressed: Binding<Bool>) -> some Scene

```

## Parameters

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
- **dialogSuppressionToggle(_:isSuppressed:)**: Enables user suppression of dialogs and alerts presented within `self`, with a custom suppression message on macOS. Unused on other platforms.
- **dialogSuppressionToggle(_:isSuppressed:)**: Enables user suppression of an alert with a custom suppression message.

