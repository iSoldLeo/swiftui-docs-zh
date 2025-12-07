--- 来源：https://developer.apple.com/documentation/SwiftUI/View/fileDialogURLEnabled(_:)

抓取时间：2025-12-02T17:30:57Z

---

# fileDialogURLEnabled(_:)

**实例方法**

在 macOS 上，配置 `fileImporter` 或 `fileMover` 以根据条件禁用显示的 URL。

## 声明

```swift
nonisolated func fileDialogURLEnabled(_ predicate: Predicate<URL>) -> some View

```

## 参数

- **predicate**：用于评估向用户显示的 URL 并根据条件禁用它们的谓词。该实现应具有常量复杂度，并且不应访问文件内容或元数据。常见用例是检查路径或文件名。

## 配置文件对话框

- **fileDialogBrowserOptions(_:)**：在 macOS 上，配置 `fileExporter`、`fileImporter` 或 `fileMover`，以提供更完善的 URL 搜索体验：包含或排除隐藏文件、允许按标签搜索等。

- **fileDialogConfirmationLabel(_:)**：在 macOS 上，配置 `fileExporter`、`fileImporter` 或 `fileMover`，为其添加自定义确认按钮标签。

- **fileDialogCustomizationID(_:)**：在 macOS 上，配置 `fileExporter`、`fileImporter` 或 `fileMover`，以保存和恢复文件对话框配置。

- **fileDialogDefaultDirectory(_:)**：配置 `fileExporter`、`fileImporter` 或 `fileMover` 以使用指定的默认目录打开。

- **fileDialogImportsUnresolvedAliases(_:)**：在 macOS 上，配置 `fileExporter`、`fileImporter` 或 `fileMover` 在用户选择别名时的行为。

- **fileDialogMessage(_:)**：在 macOS 上，配置 `fileExporter`、`fileImporter` 或 `fileMover` 向用户显示自定义文本，类似于标题。

- **FileDialogBrowserOptions**：文件对话框呈现文件系统的方式。


---
source: https://developer.apple.com/documentation/SwiftUI/View/fileDialogURLEnabled(_:)
crawled: 2025-12-02T17:30:57Z
---

# fileDialogURLEnabled(_:)

**Instance Method**

On macOS, configures the `fileImporter` or `fileMover` to conditionally disable presented URLs.

## Declaration

```swift
nonisolated func fileDialogURLEnabled(_ predicate: Predicate<URL>) -> some View

```

## Parameters

- **predicate**: The predicate that evaluates the URLs presented to the user to conditionally disable them. The implementation is expected to have constant complexity and should not access the files contents or metadata. A common use case is inspecting the path or the file name.

## Configuring a file dialog

- **fileDialogBrowserOptions(_:)**: On macOS, configures the `fileExporter`, `fileImporter`, or `fileMover` to provide a refined URL search experience: include or exclude hidden files, allow searching by tag, etc.
- **fileDialogConfirmationLabel(_:)**: On macOS, configures the `fileExporter`, `fileImporter`, or `fileMover` with a custom confirmation button label.
- **fileDialogCustomizationID(_:)**: On macOS, configures the `fileExporter`, `fileImporter`, or `fileMover` to persist and restore the file dialog configuration.
- **fileDialogDefaultDirectory(_:)**: Configures the `fileExporter`, `fileImporter`, or `fileMover` to open with the specified default directory.
- **fileDialogImportsUnresolvedAliases(_:)**: On macOS, configures the `fileExporter`, `fileImporter`, or `fileMover` behavior when a user chooses an alias.
- **fileDialogMessage(_:)**: On macOS, configures the `fileExporter`, `fileImporter`, or `fileMover` with a custom text that is presented to the user, similar to a title.
- **FileDialogBrowserOptions**: The way that file dialogs present the file system.

