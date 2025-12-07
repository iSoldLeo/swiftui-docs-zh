---
来源： https://developer.apple.com/documentation/SwiftUI/FileDialogBrowserOptions
抓取时间： 2025-12-02T17:30:58Z
---

# 文件对话框浏览器选项

**Structure**

文件对话框显示文件系统的方式。

## 声明

```swift
struct FileDialogBrowserOptions
```

## 概览

使用[fileDialogBrowserOptions(_:)](View/fileDialogBrowserOptions.zh-Hans.md)修饰符应用选项。

## 获取浏览器选项

- **displayFileExtensions**：在 iOS 上，配置 `fileExporter`、`fileImporter` 或 `fileMover`，以显示或隐藏文件扩展名。默认行为是隐藏扩展名。在 macOS 上，该选项不起作用。
- **enumeratePackages**：允许枚举软件包内容，这与默认行为不同，默认情况下软件包与文件一样是平面表示的。
- **includeHiddenFiles**：显示默认隐藏的文件。

## 配置文件对话框

- **fileDialogBrowserOptions(_:)**：在 macOS 上，配置 `fileExporter`、`fileImporter` 或 `fileMover`，以提供精致的 URL 搜索体验：包括或排除隐藏的文件，允许按标签搜索等。
- **fileDialogConfirmationLabel(_:)**：在 macOS 上，使用自定义确认按钮标签配置`fileExporter`、`fileImporter` 或 `fileMover`。
- **fileDialogCustomizationID(_:)**：在 macOS 上，配置 `fileExporter`、`fileImporter` 或 `fileMover`，以坚持和恢复文件对话框配置。
- **fileDialogDefaultDirectory(_:)**：配置 `fileExporter`、`fileImporter` 或 `fileMover`，使其使用指定的默认目录打开。
- **fileDialogImportsUnresolvedAliases(_:)**：在 macOS 上，当用户选择别名时，配置`fileExporter`、`fileImporter` 或 `fileMover` 行为。
- **fileDialogMessage(_:)**：在 macOS 上，将`fileExporter`、`fileImporter` 或`fileMover` 配置为向用户显示的自定义文本，类似于标题。
- **fileDialogURLEnabled(_:)**：在 macOS 上，配置 `fileImporter` 或 `fileMover` 以有条件禁用呈现的 URL。

## 符合

- 等价
- 可通过数组表达式（ExpressibleByArrayLiteral
- 选项集
- 原始可表示
- 可发送
- 可发送元类
- 代数集


---
source: https://developer.apple.com/documentation/SwiftUI/FileDialogBrowserOptions
crawled: 2025-12-02T17:30:58Z
---

# FileDialogBrowserOptions

**Structure**

The way that file dialogs present the file system.

## Declaration

```swift
struct FileDialogBrowserOptions
```

## Overview

Apply the options using the [fileDialogBrowserOptions(_:)](View/fileDialogBrowserOptions.zh-Hans.md) modifier.

## Getting browser options

- **displayFileExtensions**: On iOS, configures the `fileExporter`, `fileImporter`, or `fileMover` to show or hide file extensions. Default behavior is to hide them. On macOS, this option has no effect.
- **enumeratePackages**: Allows enumerating packages contents in contrast to the default behavior when packages are represented flatly, similar to files.
- **includeHiddenFiles**: Displays the files that are hidden by default.

## Configuring a file dialog

- **fileDialogBrowserOptions(_:)**: On macOS, configures the `fileExporter`, `fileImporter`, or `fileMover` to provide a refined URL search experience: include or exclude hidden files, allow searching by tag, etc.
- **fileDialogConfirmationLabel(_:)**: On macOS, configures the `fileExporter`, `fileImporter`, or `fileMover` with a custom confirmation button label.
- **fileDialogCustomizationID(_:)**: On macOS, configures the `fileExporter`, `fileImporter`, or `fileMover` to persist and restore the file dialog configuration.
- **fileDialogDefaultDirectory(_:)**: Configures the `fileExporter`, `fileImporter`, or `fileMover` to open with the specified default directory.
- **fileDialogImportsUnresolvedAliases(_:)**: On macOS, configures the `fileExporter`, `fileImporter`, or `fileMover` behavior when a user chooses an alias.
- **fileDialogMessage(_:)**: On macOS, configures the `fileExporter`, `fileImporter`, or `fileMover` with a custom text that is presented to the user, similar to a title.
- **fileDialogURLEnabled(_:)**: On macOS, configures the `fileImporter` or `fileMover` to conditionally disable presented URLs.

## Conforms To

- Equatable
- ExpressibleByArrayLiteral
- OptionSet
- RawRepresentable
- Sendable
- SendableMetatype
- SetAlgebra

