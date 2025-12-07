--- 来源：https://developer.apple.com/documentation/SwiftUI/View/fileDialogMessage(_:)

抓取时间：2025-12-02T17:30:57Z

---

# fileDialogMessage(_:)

**实例方法**

在 macOS 上，此方法配置 `fileExporter`、`fileImporter` 或 `fileMover`，并向用户显示自定义文本，类似于标题。

## 声明

```swift
nonisolated func fileDialogMessage(_ message: Text?) -> some View

```

## 参数

- **message**：用作文件对话框消息的可选文本。

## 配置文件对话框

- **fileDialogBrowserOptions(_:)**：在 macOS 上，配置 `fileExporter`、`fileImporter` 或 `fileMover`，以提供更完善的 URL 搜索体验：包含或排除隐藏文件、允许按标签搜索等。

- **fileDialogConfirmationLabel(_:)**：在 macOS 上，配置 `fileExporter`、`fileImporter` 或 `fileMover`，为其添加自定义确认按钮标签。

- **fileDialogCustomizationID(_:)**：在 macOS 上，配置 `fileExporter`、`fileImporter` 或 `fileMover`，以保存和恢复文件对话框配置。

- **fileDialogDefaultDirectory(_:)**：配置 `fileExporter`、`fileImporter` 或 `fileMover` 以使用指定的默认目录打开文件。

- **fileDialogImportsUnresolvedAliases(_:)**：在 macOS 上，配置 `fileExporter`、`fileImporter` 或 `fileMover` 在用户选择别名时的行为。

- **fileDialogURLEnabled(_:)**：在 macOS 上，配置 `fileImporter` 或 `fileMover` 以有条件地禁用显示的 URL。

- **FileDialogBrowserOptions**：文件对话框呈现文件系统的方式。


---
source: https://developer.apple.com/documentation/SwiftUI/View/fileDialogMessage(_:)
crawled: 2025-12-02T17:30:57Z
---

# fileDialogMessage(_:)

**Instance Method**

On macOS, configures the `fileExporter`, `fileImporter`, or `fileMover` with a custom text that is presented to the user, similar to a title.

## Declaration

```swift
nonisolated func fileDialogMessage(_ message: Text?) -> some View

```

## Parameters

- **message**: The optional text to use as the file dialog message.

## Configuring a file dialog

- **fileDialogBrowserOptions(_:)**: On macOS, configures the `fileExporter`, `fileImporter`, or `fileMover` to provide a refined URL search experience: include or exclude hidden files, allow searching by tag, etc.
- **fileDialogConfirmationLabel(_:)**: On macOS, configures the `fileExporter`, `fileImporter`, or `fileMover` with a custom confirmation button label.
- **fileDialogCustomizationID(_:)**: On macOS, configures the `fileExporter`, `fileImporter`, or `fileMover` to persist and restore the file dialog configuration.
- **fileDialogDefaultDirectory(_:)**: Configures the `fileExporter`, `fileImporter`, or `fileMover` to open with the specified default directory.
- **fileDialogImportsUnresolvedAliases(_:)**: On macOS, configures the `fileExporter`, `fileImporter`, or `fileMover` behavior when a user chooses an alias.
- **fileDialogURLEnabled(_:)**: On macOS, configures the `fileImporter` or `fileMover` to conditionally disable presented URLs.
- **FileDialogBrowserOptions**: The way that file dialogs present the file system.

