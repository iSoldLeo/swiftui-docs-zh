--- 来源：https://developer.apple.com/documentation/SwiftUI/Scene/dialogIcon(_:)

抓取时间：2025-12-02T17:30:33Z

---

# dialogIcon(_:)

**实例方法**

配置提示框使用的图标。

## 声明

```swift
nonisolated func dialogIcon(_ icon: Image?) -> some Scene

```

## 参数

- **icon**：用于提示框的自定义图标。传递 `nil` 将使用默认应用图标。

## 说明

在 macOS 中，此图标会替换应用的默认图标。

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
        .dialogIcon(Image(Trash.png))
    }
}
```

## 配置对话框

- **dialogIcon(_:)**：配置此视图中对话框使用的图标。

- **dialogSeverity(_:)**

- **dialogSeverity(_:)**：设置警报的严重级别。

- **dialogSuppressionToggle(isSuppressed:)**：允许用户屏蔽 `self` 中显示的对话框和警报，macOS 系统上会显示默认的屏蔽消息。其他平台未使用此功能。

- **dialogSuppressionToggle(isSuppressed:)**：允许用户屏蔽警报，并设置自定义的屏蔽消息。

- **dialogSuppressionToggle(_:isSuppressed:)**：允许用户屏蔽 `self` 中显示的对话框和警报，macOS 系统上会显示自定义的屏蔽消息。其他平台未使用此功能。

- **dialogSuppressionToggle(_:isSuppressed:)**：允许用户屏蔽警报，并设置自定义的屏蔽消息。


---
source: https://developer.apple.com/documentation/SwiftUI/Scene/dialogIcon(_:)
crawled: 2025-12-02T17:30:33Z
---

# dialogIcon(_:)

**Instance Method**

Configures the icon used by alerts.

## Declaration

```swift
nonisolated func dialogIcon(_ icon: Image?) -> some Scene

```

## Parameters

- **icon**: The custom icon to use for the alert. Passing `nil` will use the default app icon.

## Discussion

In macOS, this icon replaces the default icon of the app.

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
        .dialogIcon(Image(Trash.png))
    }
}
```

## Configuring a dialog

- **dialogIcon(_:)**: Configures the icon used by dialogs within this view.
- **dialogSeverity(_:)**
- **dialogSeverity(_:)**: Sets the severity for alerts.
- **dialogSuppressionToggle(isSuppressed:)**: Enables user suppression of dialogs and alerts presented within `self`, with a default suppression message on macOS. Unused on other platforms.
- **dialogSuppressionToggle(isSuppressed:)**: Enables user suppression of an alert with a custom suppression message.
- **dialogSuppressionToggle(_:isSuppressed:)**: Enables user suppression of dialogs and alerts presented within `self`, with a custom suppression message on macOS. Unused on other platforms.
- **dialogSuppressionToggle(_:isSuppressed:)**: Enables user suppression of an alert with a custom suppression message.

