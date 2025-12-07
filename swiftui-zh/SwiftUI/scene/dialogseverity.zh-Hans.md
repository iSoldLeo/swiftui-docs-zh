--- 来源：https://developer.apple.com/documentation/swiftui/scene/dialogseverity(_:)

抓取时间：2025-12-01T10:51:43Z

---

# dialogSeverity(_:)

**实例方法**

设置警报的严重级别。

## 声明

```swift
nonisolated func dialogSeverity(_ severity: DialogSeverity) -> some Scene

```

## 参数

- **severity**：用于警报的严重级别。

## 说明

以下示例配置了一个用于删除一定数量项目的警报。由于此操作具有破坏性且不可恢复，因此使用 `.critical` 严重级别。

```swift
struct MyApp: App {
    @State private var isShowingDialog = false

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
        .dialogSeverity(.critical)
    }
}
```

## 配置对话框

- **dialogIcon(_:)**：配置此视图中对话框使用的图标。

- **dialogIcon(_:)**：配置警报使用的图标。

- **dialogSeverity(_:)**

- **dialogSuppressionToggle(isSuppressed:)**：启用用户屏蔽 `self` 中显示的对话框和警报，macOS 系统使用默认屏蔽消息。其他平台未使用此功能。

- **dialogSuppressionToggle(isSuppressed:)**：启用用户屏蔽警报，并可使用自定义屏蔽消息。

- **dialogSuppressionToggle(_:isSuppressed:)**：启用用户屏蔽 `self` 中显示的对话框和警报，macOS 系统使用自定义屏蔽消息。其他平台未使用此功能。

- **dialogSuppressionToggle(_:isSuppressed:)**：允许用户使用自定义抑制消息来抑制警报。


---
source: https://developer.apple.com/documentation/swiftui/scene/dialogseverity(_:)
crawled: 2025-12-01T10:51:43Z
---

# dialogSeverity(_:)

**Instance Method**

Sets the severity for alerts.

## Declaration

```swift
nonisolated func dialogSeverity(_ severity: DialogSeverity) -> some Scene

```

## Parameters

- **severity**: The severity to use for alerts.

## Discussion

The following example configures an alert for erasing some number of items. Since this operation is destructive and non-recoverable, a `.critical` severity is used.

```swift
struct MyApp: App {
    @State private var isShowingDialog = false

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
        .dialogSeverity(.critical)
    }
}
```

## Configuring a dialog

- **dialogIcon(_:)**: Configures the icon used by dialogs within this view.
- **dialogIcon(_:)**: Configures the icon used by alerts.
- **dialogSeverity(_:)**
- **dialogSuppressionToggle(isSuppressed:)**: Enables user suppression of dialogs and alerts presented within `self`, with a default suppression message on macOS. Unused on other platforms.
- **dialogSuppressionToggle(isSuppressed:)**: Enables user suppression of an alert with a custom suppression message.
- **dialogSuppressionToggle(_:isSuppressed:)**: Enables user suppression of dialogs and alerts presented within `self`, with a custom suppression message on macOS. Unused on other platforms.
- **dialogSuppressionToggle(_:isSuppressed:)**: Enables user suppression of an alert with a custom suppression message.

