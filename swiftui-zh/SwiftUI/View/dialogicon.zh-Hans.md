--- 来源：https://developer.apple.com/documentation/swiftui/view/dialogicon(_:)

抓取时间：2025-12-01T10:51:42Z

---

# dialogIcon(_:)

**实例方法**

配置此视图中对话框使用的图标。

## 声明

```swift
nonisolated func dialogIcon(_ icon: Image?) -> some View

```

## 参数

- **icon**：用于确认对话框和提示框的自定义图标。传递 `nil` 将使用默认应用图标。

## 说明

在 macOS 上，此图标会替换应用的默认图标。

在 watchOS 上，此图标将显示在所有对话框中。

此修饰符在其他平台上无效。

以下示例配置一个带有自定义图像的 `confirmationDialog`。

```swift
Button("Delete items") {
    isShowingDialog = true
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
.dialogIcon(Image(...))
```

## 配置对话框

- **dialogIcon(_:)**：配置警报使用的图标。

- **dialogSeverity(_:)**

- **dialogSeverity(_:)**：设置警报的严重级别。

- **dialogSuppressionToggle(isSuppressed:)**：允许用户屏蔽 `self` 中显示的对话框和警报，macOS 系统上会显示默认的屏蔽消息。其他平台未使用此功能。

- **dialogSuppressionToggle(isSuppressed:)**：允许用户屏蔽带有自定义屏蔽消息的警报。

- **dialogSuppressionToggle(_:isSuppressed:)**：允许用户在 macOS 系统上使用自定义屏蔽消息来屏蔽 `self` 中显示的对话框和警报。其他平台未使用此功能。

- **dialogSuppressionToggle(_:isSuppressed:)**：允许用户使用自定义屏蔽消息来屏蔽警报。


---
source: https://developer.apple.com/documentation/swiftui/view/dialogicon(_:)
crawled: 2025-12-01T10:51:42Z
---

# dialogIcon(_:)

**Instance Method**

Configures the icon used by dialogs within this view.

## Declaration

```swift
nonisolated func dialogIcon(_ icon: Image?) -> some View

```

## Parameters

- **icon**: The custom icon to use for confirmation dialogs and alerts. Passing `nil` will use the default app icon.

## Discussion

On macOS, this icon replaces the default icon of the app.

On watchOS, this icon will be shown in any dialogs presented.

This modifier has no effect on other platforms.

The following example configures a `confirmationDialog` with a custom image.

```swift
Button("Delete items") {
    isShowingDialog = true
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
.dialogIcon(Image(...))
```

## Configuring a dialog

- **dialogIcon(_:)**: Configures the icon used by alerts.
- **dialogSeverity(_:)**
- **dialogSeverity(_:)**: Sets the severity for alerts.
- **dialogSuppressionToggle(isSuppressed:)**: Enables user suppression of dialogs and alerts presented within `self`, with a default suppression message on macOS. Unused on other platforms.
- **dialogSuppressionToggle(isSuppressed:)**: Enables user suppression of an alert with a custom suppression message.
- **dialogSuppressionToggle(_:isSuppressed:)**: Enables user suppression of dialogs and alerts presented within `self`, with a custom suppression message on macOS. Unused on other platforms.
- **dialogSuppressionToggle(_:isSuppressed:)**: Enables user suppression of an alert with a custom suppression message.

