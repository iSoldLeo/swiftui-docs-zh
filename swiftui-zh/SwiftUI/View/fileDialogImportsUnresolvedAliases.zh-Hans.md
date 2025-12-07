--- 来源：https://developer.apple.com/documentation/SwiftUI/View/fileDialogImportsUnresolvedAliases(_:)

抓取时间：2025-12-02T17:30:56Z

---

# fileDialogImportsUnresolvedAliases(_:)

**实例方法**

在 macOS 上，配置用户选择别名时 `fileExporter`、`fileImporter` 或 `fileMover` 的行为。

## 声明

```swift
nonisolated func fileDialogImportsUnresolvedAliases(_ imports: Bool) -> some View

```

## 参数

- **imports**：一个布尔值，指示用户选择别名时应用程序接收的是未解析的 URL 还是已解析的 URL。

## 讨论

默认情况下，文件对话框会解析别名并提供所选别名所指向项目的 URL。此修饰符允许控制此行为：如果应用程序不希望文件对话框解析别名，请传递 `true`。

## 配置文件对话框

- **fileDialogBrowserOptions(_:)**：在 macOS 上，配置 `fileExporter`、`fileImporter` 或 `fileMover` 以提供更精细的 URL 搜索体验：包含或排除隐藏文件、允许按标签搜索等。

- **fileDialogConfirmationLabel(_:)**：在 macOS 上，配置 `fileExporter`、`fileImporter` 或 `fileMover`，为其添加自定义确认按钮标签。

- **fileDialogCustomizationID(_:)**：在 macOS 系统中，配置 `fileExporter`、`fileImporter` 或 `fileMover` 以持久化和恢复文件对话框配置。

- **fileDialogDefaultDirectory(_:)**：配置 `fileExporter`、`fileImporter` 或 `fileMover` 以使用指定的默认目录打开文件。

- **fileDialogMessage(_:)**：在 macOS 系统中，配置 `fileExporter`、`fileImporter` 或 `fileMover`，使其显示类似标题的自定义文本。

- **fileDialogURLEnabled(_:)**：在 macOS 系统中，配置 `fileImporter` 或 `fileMover` 以根据条件禁用显示的 URL。

- **FileDialogBrowserOptions**：文件对话框呈现文件系统的方式。


---
source: https://developer.apple.com/documentation/SwiftUI/View/fileDialogImportsUnresolvedAliases(_:)
crawled: 2025-12-02T17:30:56Z
---

# fileDialogImportsUnresolvedAliases(_:)

**Instance Method**

On macOS, configures the `fileExporter`, `fileImporter`, or `fileMover` behavior when a user chooses an alias.

## Declaration

```swift
nonisolated func fileDialogImportsUnresolvedAliases(_ imports: Bool) -> some View

```

## Parameters

- **imports**: A Boolean value that indicates if the application receives unresolved or resolved URLs when a user chooses aliases.

## Discussion

By default, file dialogs resolve aliases and provide the URL of the item referred to by the chosen alias. This modifier allows control of this behavior: pass `true` if the application doesn’t want file dialog to resolve aliases.

## Configuring a file dialog

- **fileDialogBrowserOptions(_:)**: On macOS, configures the `fileExporter`, `fileImporter`, or `fileMover` to provide a refined URL search experience: include or exclude hidden files, allow searching by tag, etc.
- **fileDialogConfirmationLabel(_:)**: On macOS, configures the `fileExporter`, `fileImporter`, or `fileMover` with a custom confirmation button label.
- **fileDialogCustomizationID(_:)**: On macOS, configures the `fileExporter`, `fileImporter`, or `fileMover` to persist and restore the file dialog configuration.
- **fileDialogDefaultDirectory(_:)**: Configures the `fileExporter`, `fileImporter`, or `fileMover` to open with the specified default directory.
- **fileDialogMessage(_:)**: On macOS, configures the `fileExporter`, `fileImporter`, or `fileMover` with a custom text that is presented to the user, similar to a title.
- **fileDialogURLEnabled(_:)**: On macOS, configures the `fileImporter` or `fileMover` to conditionally disable presented URLs.
- **FileDialogBrowserOptions**: The way that file dialogs present the file system.

