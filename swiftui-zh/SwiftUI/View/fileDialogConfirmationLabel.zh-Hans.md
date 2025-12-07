--- 来源：https://developer.apple.com/documentation/SwiftUI/View/fileDialogConfirmationLabel(_:)

抓取时间：2025-11-30T21:15:57Z

---

# fileDialogConfirmationLabel(_:)

**实例方法**

在 macOS 上，此方法用于配置 `fileExporter`、`fileImporter` 或 `fileMover`，并为其显示自定义确认按钮标签。

## 声明

```swift
nonisolated func fileDialogConfirmationLabel(_ label: LocalizedStringResource) -> some View

```

## 参数

- **label**：要显示的本地化字符串资源。

## 配置文件对话框

- **fileDialogBrowserOptions(_:)**：在 macOS 上，配置 `fileExporter`、`fileImporter` 或 `fileMover`，以提供更完善的 URL 搜索体验：包含或排除隐藏文件、允许按标签搜索等。

- **fileDialogCustomizationID(_:)**：在 macOS 上，配置 `fileExporter`、`fileImporter` 或 `fileMover`，以保存和恢复文件对话框配置。

- **fileDialogDefaultDirectory(_:)**：配置 `fileExporter`、`fileImporter` 或 `fileMover`，以使用指定的默认目录打开文件。

- **fileDialogImportsUnresolvedAliases(_:)**：在 macOS 系统中，配置用户选择别名时 `fileExporter`、`fileImporter` 或 `fileMover` 的行为。

- **fileDialogMessage(_:)**：在 macOS 系统中，配置 `fileExporter`、`fileImporter` 或 `fileMover`，使其显示类似标题的自定义文本。

- **fileDialogURLEnabled(_:)**：在 macOS 系统中，配置 `fileImporter` 或 `fileMover`，以在特定情况下禁用显示的 URL。

- **FileDialogBrowserOptions**：文件对话框呈现文件系统的方式。


---
source: https://developer.apple.com/documentation/SwiftUI/View/fileDialogConfirmationLabel(_:)
crawled: 2025-11-30T21:15:57Z
---

# fileDialogConfirmationLabel(_:)

**Instance Method**

On macOS, configures the `fileExporter`, `fileImporter`, or `fileMover` with a custom confirmation button label.

## Declaration

```swift
nonisolated func fileDialogConfirmationLabel(_ label: LocalizedStringResource) -> some View

```

## Parameters

- **label**: The localized string resource to display.

## Configuring a file dialog

- **fileDialogBrowserOptions(_:)**: On macOS, configures the `fileExporter`, `fileImporter`, or `fileMover` to provide a refined URL search experience: include or exclude hidden files, allow searching by tag, etc.
- **fileDialogCustomizationID(_:)**: On macOS, configures the `fileExporter`, `fileImporter`, or `fileMover` to persist and restore the file dialog configuration.
- **fileDialogDefaultDirectory(_:)**: Configures the `fileExporter`, `fileImporter`, or `fileMover` to open with the specified default directory.
- **fileDialogImportsUnresolvedAliases(_:)**: On macOS, configures the `fileExporter`, `fileImporter`, or `fileMover` behavior when a user chooses an alias.
- **fileDialogMessage(_:)**: On macOS, configures the `fileExporter`, `fileImporter`, or `fileMover` with a custom text that is presented to the user, similar to a title.
- **fileDialogURLEnabled(_:)**: On macOS, configures the `fileImporter` or `fileMover` to conditionally disable presented URLs.
- **FileDialogBrowserOptions**: The way that file dialogs present the file system.

