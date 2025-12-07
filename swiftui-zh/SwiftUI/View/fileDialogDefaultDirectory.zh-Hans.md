--- 来源：https://developer.apple.com/documentation/SwiftUI/View/fileDialogDefaultDirectory(_:)

抓取时间：2025-11-30T21:15:58Z

---

# fileDialogDefaultDirectory(_:)

**实例方法**

配置 `fileExporter`、`fileImporter` 或 `fileMover` 以使用指定的默认目录打开文件对话框。

## 声明

```swift
nonisolated func fileDialogDefaultDirectory(_ defaultDirectory: URL?) -> some View

```

## 参数

- **defaultDirectory**：系统文件对话框启动时显示的目录。如果给定的文件对话框具有 `fileDialogCustomizationID`，则存储用户选择的目录并随后使用该目录打开文件对话框，忽略此修饰符中提供的默认值。

## 配置文件对话框

- **fileDialogBrowserOptions(_:)**：在 macOS 上，配置 `fileExporter`、`fileImporter` 或 `fileMover`，以提供更完善的 URL 搜索体验：包含或排除隐藏文件、允许按标签搜索等。

- **fileDialogConfirmationLabel(_:)**：在 macOS 上，配置 `fileExporter`、`fileImporter` 或 `fileMover`，为其添加自定义确认按钮标签。

- **fileDialogCustomizationID(_:)**：在 macOS 上，配置 `fileExporter`、`fileImporter` 或 `fileMover`，以保存和恢复文件对话框配置。

- **fileDialogImportsUnresolvedAliases(_:)**：在 macOS 系统中，配置用户选择别名时 `fileExporter`、`fileImporter` 或 `fileMover` 的行为。

- **fileDialogMessage(_:)**：在 macOS 系统中，配置 `fileExporter`、`fileImporter` 或 `fileMover`，使其显示类似于标题的自定义文本。

- **fileDialogURLEnabled(_:)**：在 macOS 系统中，配置 `fileImporter` 或 `fileMover`，以在特定情况下禁用显示的 URL。

- **FileDialogBrowserOptions**：文件对话框呈现文件系统的方式。


---
source: https://developer.apple.com/documentation/SwiftUI/View/fileDialogDefaultDirectory(_:)
crawled: 2025-11-30T21:15:58Z
---

# fileDialogDefaultDirectory(_:)

**Instance Method**

Configures the `fileExporter`, `fileImporter`, or `fileMover` to open with the specified default directory.

## Declaration

```swift
nonisolated func fileDialogDefaultDirectory(_ defaultDirectory: URL?) -> some View

```

## Parameters

- **defaultDirectory**: The directory to show when the system file dialog launches. If the given file dialog has a `fileDialogCustomizationID` if stores the user-chosen directory and subsequently opens with it, ignoring the default value provided in this modifier.

## Configuring a file dialog

- **fileDialogBrowserOptions(_:)**: On macOS, configures the `fileExporter`, `fileImporter`, or `fileMover` to provide a refined URL search experience: include or exclude hidden files, allow searching by tag, etc.
- **fileDialogConfirmationLabel(_:)**: On macOS, configures the `fileExporter`, `fileImporter`, or `fileMover` with a custom confirmation button label.
- **fileDialogCustomizationID(_:)**: On macOS, configures the `fileExporter`, `fileImporter`, or `fileMover` to persist and restore the file dialog configuration.
- **fileDialogImportsUnresolvedAliases(_:)**: On macOS, configures the `fileExporter`, `fileImporter`, or `fileMover` behavior when a user chooses an alias.
- **fileDialogMessage(_:)**: On macOS, configures the `fileExporter`, `fileImporter`, or `fileMover` with a custom text that is presented to the user, similar to a title.
- **fileDialogURLEnabled(_:)**: On macOS, configures the `fileImporter` or `fileMover` to conditionally disable presented URLs.
- **FileDialogBrowserOptions**: The way that file dialogs present the file system.

