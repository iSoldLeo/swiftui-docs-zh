--- 来源：https://developer.apple.com/documentation/SwiftUI/View/fileDialogCustomizationID(_:)

抓取时间：2025-12-02T17:30:54Z

---

# fileDialogCustomizationID(_:)

**实例方法**

在 macOS 上，配置 `fileExporter`、`fileImporter` 或 `fileMover` 以持久化和恢复文件对话框配置。

## 声明

```swift
nonisolated func fileDialogCustomizationID(_ id: String) -> some View

```

## 参数

- **id**：配置的标识符。

## 说明

除其他参数外，它还存储当前目录、视图样式（例如，图标、列表、列）、最近访问位置和展开窗口大小。它能够带来更佳的用户体验；例如，导入图像时，用户可能会切换到“图标”视图，但在其他情况下，“列表”视图可能更方便。文件对话框会存储这些设置，并在每次显示面板之前应用这些设置。如果未提供设置，则每次启动时，文件对话框都会使用默认配置。

## 配置文件对话框

- **fileDialogBrowserOptions(_:)**：在 macOS 上，配置 `fileExporter`、`fileImporter` 或 `fileMover`，以提供更完善的 URL 搜索体验：包含或排除隐藏文件、允许按标签搜索等。

- **fileDialogConfirmationLabel(_:)**：在 macOS 上，配置 `fileExporter`、`fileImporter` 或 `fileMover`，为其添加自定义确认按钮标签。

- **fileDialogDefaultDirectory(_:)**：配置 `fileExporter`、`fileImporter` 或 `fileMover` 以使用指定的默认目录打开。

- **fileDialogImportsUnresolvedAliases(_:)**：在 macOS 上，配置 `fileExporter`、`fileImporter` 或 `fileMover` 在用户选择别名时的行为。

- **fileDialogMessage(_:)**：在 macOS 上，配置 `fileExporter`、`fileImporter` 或 `fileMover`，使其显示类似于标题的自定义文本。

- **fileDialogURLEnabled(_:)**：在 macOS 系统中，配置 `fileImporter` 或 `fileMover` 以根据条件禁用显示的 URL。

- **FileDialogBrowserOptions**：文件对话框呈现文件系统的方式。


---
source: https://developer.apple.com/documentation/SwiftUI/View/fileDialogCustomizationID(_:)
crawled: 2025-12-02T17:30:54Z
---

# fileDialogCustomizationID(_:)

**Instance Method**

On macOS, configures the `fileExporter`, `fileImporter`, or `fileMover` to persist and restore the file dialog configuration.

## Declaration

```swift
nonisolated func fileDialogCustomizationID(_ id: String) -> some View

```

## Parameters

- **id**: An identifier of the configuration.

## Discussion

Among other parameters, it stores the current directory, view style (e.g., Icons, List, Columns), recent places, and expanded window size. It enables a refined user experience; for example, when importing an image, the user might switch to the Icons view, but the List view could be more convenient in another context. The file dialog stores these settings and applies them every time before presenting the panel. If not provided, on every launch, the file dialog uses the default configuration.

## Configuring a file dialog

- **fileDialogBrowserOptions(_:)**: On macOS, configures the `fileExporter`, `fileImporter`, or `fileMover` to provide a refined URL search experience: include or exclude hidden files, allow searching by tag, etc.
- **fileDialogConfirmationLabel(_:)**: On macOS, configures the `fileExporter`, `fileImporter`, or `fileMover` with a custom confirmation button label.
- **fileDialogDefaultDirectory(_:)**: Configures the `fileExporter`, `fileImporter`, or `fileMover` to open with the specified default directory.
- **fileDialogImportsUnresolvedAliases(_:)**: On macOS, configures the `fileExporter`, `fileImporter`, or `fileMover` behavior when a user chooses an alias.
- **fileDialogMessage(_:)**: On macOS, configures the `fileExporter`, `fileImporter`, or `fileMover` with a custom text that is presented to the user, similar to a title.
- **fileDialogURLEnabled(_:)**: On macOS, configures the `fileImporter` or `fileMover` to conditionally disable presented URLs.
- **FileDialogBrowserOptions**: The way that file dialogs present the file system.

