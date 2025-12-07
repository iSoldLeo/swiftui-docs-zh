--- 来源：https://developer.apple.com/documentation/SwiftUI/Modal-presentations
抓取时间：2025-12-02T17:20:46Z

---

# 模态视图

**API 集合**

在单独的视图中呈现内容，提供专注的交互。

## 概述

为了吸引用户注意某个重要的、范围较窄的任务，您可以显示模态视图，例如警告框、弹出框、表单或确认对话框。

在 SwiftUI 中，您可以使用视图修饰符创建模态视图，该修饰符定义了视图的外观以及 SwiftUI 显示它的条件。SwiftUI 会检测条件何时发生变化，并自动显示模态视图。由于您为触发模态视图的条件提供了一个 [Binding](Binding.zh-Hans.md)，因此当用户关闭模态视图时，SwiftUI 可以重置底层值。

设计指南请参见《人机界面指南》中的[doc://com.apple.documentation/design/Human-Interface-Guidelines/modality]。

## 配置对话框

- **DialogSeverity**：警报或确认对话框的严重程度。

## 显示工作表、封面或弹出窗口

- **sheet(isPresented:onDismiss:content:)**：当您提供的布尔值绑定为真时，显示工作表。

- **sheet(item:onDismiss:content:)**：使用给定项作为工作表内容的数据源来显示工作表。

- **fullScreenCover(isPresented:onDismiss:content:)**：当您提供的布尔值绑定为真时，显示一个尽可能覆盖屏幕的模态视图。

- **fullScreenCover(item:onDismiss:content:)**：使用您提供的绑定作为工作表内容的数据源，显示一个尽可能覆盖屏幕的模态视图。

- **popover(item:attachmentAnchor:arrowEdge:content:)**：使用指定项作为弹出框内容的数据源来显示弹出框。

- **popover(isPresented:attachmentAnchor:arrowEdge:content:)**：当满足指定条件时显示弹出框。

- **PopoverAttachmentAnchor**：弹出框的附件锚点。

## 调整演示文稿大小

- **presentationCompactAdaptation(horizontal:vertical:)**：指定如何将演示文稿调整为水平和垂直方向的紧凑尺寸类别。

- **presentationCompactAdaptation(_:)**：指定如何将演示文稿调整为紧凑尺寸类别。

- **PresentationAdaptation**：将演示文稿调整为不同尺寸类别的策略。

- **presentationSizing(_:)**：设置包含演示文稿的大小。

- **PresentationSizing**：定义演示文稿内容大小以及演示文稿大小如何随内容大小变化而调整的类型。

- **PresentationSizingRoot**：为演示文稿提供的具有已定义演示文稿大小的视图代理。

- **PresentationSizingContext**：关于演示文稿的上下文信息。

## 配置工作表高度

- **presentationDetents(_:)**：设置包含工作表的可用位置。

- **presentationDetents(_:selection:)**：设置包含工作表的可用位置，允许您以编程方式控制当前选定的位置。

- **presentationContentInteraction(_:)**：配置演示文稿上的滑动操作行为。

- **presentationDragIndicator(_:)**：设置工作表顶部拖拽指示器的可见性。

- **PresentationDetent**：表示工作表自然放置高度的类型。

- **CustomPresentationDetent**：定义具有计算高度的自定义定位点。

- **PresentationContentInteraction**：可用于影响演示文稿对滑动操作响应的行为。

## 设置工作表及其背景的样式

- **presentationCornerRadius(_:)**：请求演示文稿具有特定的圆角半径。

- **presentationBackground(_:)**：使用形状样式设置包含工作表的演示文稿背景。

- **presentationBackground(alignment:content:)**：将包含工作表的演示文稿背景设置为自定义视图。

- **presentationBackgroundInteraction(_:)**：控制用户是否可以与演示文稿背后的视图进行交互。

- **PresentationBackgroundInteraction**：演示文稿背后的视图可用的交互类型。

## 显示警告

- **AlertScene**：将自身渲染为独立警告对话框的场景。

- **alert(_:isPresented:actions:)**：当给定条件为真时，显示警告，并使用文本视图作为标题。

- **alert(_:isPresented:presenting:actions:)**：使用给定数据生成警告内容，并使用文本视图作为标题。

- **alert(isPresented:error:actions:)**：当出现错误时，显示警告。

- **alert(_:isPresented:actions:message:)**：当给定条件为真时，显示带有消息的警告，并使用文本视图作为标题。

- **alert(_:isPresented:presenting:actions:message:)**：根据给定数据生成警报内容，并使用文本视图显示标题，从而显示包含消息的警报。

- **alert(isPresented:error:actions:message:)**：出现错误时，显示包含消息的警报。

## 获取操作确认

- **confirmationDialog(_:isPresented:titleVisibility:actions:)**：当满足给定条件时，显示确认对话框，并使用文本视图显示标题。

- **confirmationDialog(_:isPresented:titleVisibility:presenting:actions:)**：根据数据生成确认对话框内容，并使用文本视图显示标题，从而显示确认对话框。

- **dismissalConfirmationDialog(_:shouldPresent:actions:)**：触发关闭操作时，显示确认对话框。

## 显示包含消息的确认对话框

- **confirmationDialog(_:isPresented:titleVisibility:actions:message:)**：当满足给定条件时，显示包含消息的确认对话框，并使用文本视图显示标题。

- **confirmationDialog(_:isPresented:titleVisibility:presenting:actions:message:)**：显示一个确认对话框，对话框内容由数据生成，并包含一个文本视图。

- **dismissalConfirmationDialog(_:shouldPresent:actions:message:)**：当触发关闭操作时，显示一个确认对话框。

## 配置对话框

- **dialogIcon(_:)**：配置此视图中对话框使用的图标。

- **dialogIcon(_:)**：配置警报使用的图标。

- **dialogSeverity(_:)**

- **dialogSeverity(_:)**：设置警报的严重级别。

- **dialogSuppressionToggle(isSuppressed:)**：允许用户屏蔽在 `self` 中显示的对话框和警报，macOS 上会显示默认的屏蔽消息。其他平台未使用此功能。

- **dialogSuppressionToggle(isSuppressed:)**：允许用户使用自定义抑制消息来抑制警报。

- **dialogSuppressionToggle(_:isSuppressed:)**：允许用户使用自定义抑制消息来抑制 macOS 系统上 `self` 中显示的对话框和警报。其他平台未使用此功能。

- **dialogSuppressionToggle(_:isSuppressed:)**：允许用户使用自定义抑制消息来抑制警报。

## 导出到文件

- **fileExporter(isPresented:document:contentType:defaultFilename:onCompletion:)**：提供一个系统接口，用于将存储在值类型（例如结构体）中的文档导出到磁盘上的文件。

- **fileExporter(isPresented:documents:contentType:onCompletion:)**：提供一个系统接口，用于将值类型文档集合导出到磁盘上的文件。

- **fileExporter(isPresented:document:contentTypes:defaultFilename:onCompletion:onCancellation:)**：提供一个系统界面，允许用户将 `FileDocument` 导出到磁盘上的文件。

- **fileExporter(isPresented:documents:contentTypes:onCompletion:onCancellation:)**：提供一个系统对话框，允许用户将符合 `FileDocument` 规范的文档集合导出到磁盘上的文件。

- **fileExporter(isPresented:item:contentTypes:defaultFilename:onCompletion:onCancellation:)**：提供一个系统界面，允许用户将 `Transferable` 项目导出到磁盘上的文件。

- **fileExporter(isPresented:items:contentTypes:onCompletion:onCancellation:)**：提供一个系统界面，允许用户将项目集合导出到磁盘上的文件。

- **fileExporterFilenameLabel(_:)**：在 macOS 系统上，为 `fileExporter` 的文件名字段配置标签。

## 从文件导入

- **fileImporter(isPresented:allowedContentTypes:allowsMultipleSelection:onCompletion:)**：提供一个系统界面，允许用户导入多个文件。

- **fileImporter(isPresented:allowedContentTypes:onCompletion:)**：提供一个系统界面，允许用户导入现有文件。

- **fileImporter(isPresented:allowedContentTypes:allowsMultipleSelection:onCompletion:onCancellation:)**：提供一个系统对话框，允许用户导入多个文件。

## 移动文件

- **fileMover(isPresented:file:onCompletion:)**：提供一个系统界面，允许用户将现有文件移动到新位置。

- **fileMover(isPresented:files:onCompletion:)**：提供一个系统界面，允许用户将多个现有文件移动到新位置。

- **fileMover(isPresented:file:onCompletion:onCancellation:)**：提供一个系统对话框，允许用户将现有文件移动到新位置。

- **fileMover(isPresented:files:onCompletion:onCancellation:)**：显示一个系统对话框，允许用户将一组现有文件移动到新位置。

## 配置文件对话框

- **fileDialogBrowserOptions(_:)**：在 macOS 上，配置 `fileExporter`、`fileImporter` 或 `fileMover`，以提供更完善的 URL 搜索体验：包含或排除隐藏文件、允许按标签搜索等。

- **fileDialogConfirmationLabel(_:)**：在 macOS 上，配置 `fileExporter`、`fileImporter` 或 `fileMover`，为其添加自定义确认按钮标签。

- **fileDialogCustomizationID(_:)**：在 macOS 上，配置 `fileExporter`、`fileImporter` 或 `fileMover` 以持久化和恢复文件对话框配置。

- **fileDialogDefaultDirectory(_:)**：配置 `fileExporter`、`fileImporter` 或 `fileMover` 以使用指定的默认目录打开文件。

- **fileDialogImportsUnresolvedAliases(_:)**：在 macOS 上，配置 `fileExporter`、`fileImporter` 或 `fileMover` 在用户选择别名时的行为。

- **fileDialogMessage(_:)**：在 macOS 系统中，配置 `fileExporter`、`fileImporter` 或 `fileMover`，使其显示类似标题的自定义文本。

- **fileDialogURLEnabled(_:)**：在 macOS 系统中，配置 `fileImporter` 或 `fileMover`，使其能够有条件地禁用显示的 URL。

- **FileDialogBrowserOptions**：文件对话框显示文件系统的方式。

## 显示检查器

- **inspector(isPresented:content:)**：在视图层次结构中的指定位置插入检查器。

- **inspectorColumnWidth(_:)**：设置以尾随列形式呈现的包含此视图的检查器的固定首选宽度。

- **inspectorColumnWidth(min:ideal:max:)**：设置以尾随列形式呈现的检查器的灵活首选宽度。

## 关闭呈现

- **isPresented**：一个布尔值，指示与此环境关联的视图当前是否处于呈现状态。

- **dismiss**：关闭当前呈现的操作。

- **DismissAction**：关闭呈现的操作。

- **interactiveDismissDisabled(_:)**：有条件地阻止交互式关闭弹出框、工作表和检查器等呈现方式。

## 已弃用的模态呈现

- **Alert**：警报呈现的表示形式。

- **ActionSheet**：操作表的呈现方式。

## 应用结构

- **应用组织结构**：定义应用的入口点和顶层结构。

- **Scenes**：声明构成应用各个部分的用户界面分组。

- **Windows**：在单个窗口或窗口集合中显示用户界面内容。

- **沉浸式空间**：在用户的周围环境中显示无限内容。

- **Documents**：允许用户打开和管理文档。

- **Navigation**：允许用户在场景中切换应用视图层级结构的不同部分。

- **Toolbars**：提供对常用命令和控件的快速访问。

- **Search**：允许用户在您的应用内搜索文本或其他内容。

- **应用扩展**：将您应用的基本功能扩展到系统的其他部分，例如添加小部件。


---
source: https://developer.apple.com/documentation/SwiftUI/Modal-presentations
crawled: 2025-12-02T17:20:46Z
---

# Modal presentations

**API Collection**

Present content in a separate view that offers focused interaction.

## Overview

To draw attention to an important, narrowly scoped task, you display a modal presentation, like an alert, popover, sheet, or confirmation dialog.



In SwiftUI, you create a modal presentation using a view modifier that defines how the presentation looks and the condition under which SwiftUI presents it. SwiftUI detects when the condition changes and makes the presentation for you. Because you provide a [Binding](Binding.zh-Hans.md) to the condition that initiates the presentation, SwiftUI can reset the underlying value when the user dismisses the presentation.

For design guidance, see [doc://com.apple.documentation/design/Human-Interface-Guidelines/modality] in the Human Interface Guidelines.

## Configuring a dialog

- **DialogSeverity**: The severity of an alert or confirmation dialog.

## Showing a sheet, cover, or popover

- **sheet(isPresented:onDismiss:content:)**: Presents a sheet when a binding to a Boolean value that you provide is true.
- **sheet(item:onDismiss:content:)**: Presents a sheet using the given item as a data source for the sheet’s content.
- **fullScreenCover(isPresented:onDismiss:content:)**: Presents a modal view that covers as much of the screen as possible when binding to a Boolean value you provide is true.
- **fullScreenCover(item:onDismiss:content:)**: Presents a modal view that covers as much of the screen as possible using the binding you provide as a data source for the sheet’s content.
- **popover(item:attachmentAnchor:arrowEdge:content:)**: Presents a popover using the given item as a data source for the popover’s content.
- **popover(isPresented:attachmentAnchor:arrowEdge:content:)**: Presents a popover when a given condition is true.
- **PopoverAttachmentAnchor**: An attachment anchor for a popover.

## Adapting a presentation size

- **presentationCompactAdaptation(horizontal:vertical:)**: Specifies how to adapt a presentation to horizontally and vertically compact size classes.
- **presentationCompactAdaptation(_:)**: Specifies how to adapt a presentation to compact size classes.
- **PresentationAdaptation**: Strategies for adapting a presentation to a different size class.
- **presentationSizing(_:)**: Sets the sizing of the containing presentation.
- **PresentationSizing**: A type that defines the size of the presentation content and how the presentation size adjusts to its content’s size changing.
- **PresentationSizingRoot**: A proxy to a view provided to the presentation with a defined presentation size.
- **PresentationSizingContext**: Contextual information about a presentation.

## Configuring a sheet’s height

- **presentationDetents(_:)**: Sets the available detents for the enclosing sheet.
- **presentationDetents(_:selection:)**: Sets the available detents for the enclosing sheet, giving you programmatic control of the currently selected detent.
- **presentationContentInteraction(_:)**: Configures the behavior of swipe gestures on a presentation.
- **presentationDragIndicator(_:)**: Sets the visibility of the drag indicator on top of a sheet.
- **PresentationDetent**: A type that represents a height where a sheet naturally rests.
- **CustomPresentationDetent**: The definition of a custom detent with a calculated height.
- **PresentationContentInteraction**: A behavior that you can use to influence how a presentation responds to swipe gestures.

## Styling a sheet and its background

- **presentationCornerRadius(_:)**: Requests that the presentation have a specific corner radius.
- **presentationBackground(_:)**: Sets the presentation background of the enclosing sheet using a shape style.
- **presentationBackground(alignment:content:)**: Sets the presentation background of the enclosing sheet to a custom view.
- **presentationBackgroundInteraction(_:)**: Controls whether people can interact with the view behind a presentation.
- **PresentationBackgroundInteraction**: The kinds of interaction available to views behind a presentation.

## Presenting an alert

- **AlertScene**: A scene that renders itself as a standalone alert dialog.
- **alert(_:isPresented:actions:)**: Presents an alert when a given condition is true, using a text view for the title.
- **alert(_:isPresented:presenting:actions:)**: Presents an alert using the given data to produce the alert’s content and a text view as a title.
- **alert(isPresented:error:actions:)**: Presents an alert when an error is present.
- **alert(_:isPresented:actions:message:)**: Presents an alert with a message when a given condition is true using a text view as a title.
- **alert(_:isPresented:presenting:actions:message:)**: Presents an alert with a message using the given data to produce the alert’s content and a text view for a title.
- **alert(isPresented:error:actions:message:)**: Presents an alert with a message when an error is present.

## Getting confirmation for an action

- **confirmationDialog(_:isPresented:titleVisibility:actions:)**: Presents a confirmation dialog when a given condition is true, using a text view for the title.
- **confirmationDialog(_:isPresented:titleVisibility:presenting:actions:)**: Presents a confirmation dialog using data to produce the dialog’s content and a text view for the title.
- **dismissalConfirmationDialog(_:shouldPresent:actions:)**: Presents a confirmation dialog when a dismiss action has been triggered.

## Showing a confirmation dialog with a message

- **confirmationDialog(_:isPresented:titleVisibility:actions:message:)**: Presents a confirmation dialog with a message when a given condition is true, using a text view for the title.
- **confirmationDialog(_:isPresented:titleVisibility:presenting:actions:message:)**: Presents a confirmation dialog with a message using data to produce the dialog’s content and a text view for the message.
- **dismissalConfirmationDialog(_:shouldPresent:actions:message:)**: Presents a confirmation dialog when a dismiss action has been triggered.

## Configuring a dialog

- **dialogIcon(_:)**: Configures the icon used by dialogs within this view.
- **dialogIcon(_:)**: Configures the icon used by alerts.
- **dialogSeverity(_:)**
- **dialogSeverity(_:)**: Sets the severity for alerts.
- **dialogSuppressionToggle(isSuppressed:)**: Enables user suppression of dialogs and alerts presented within `self`, with a default suppression message on macOS. Unused on other platforms.
- **dialogSuppressionToggle(isSuppressed:)**: Enables user suppression of an alert with a custom suppression message.
- **dialogSuppressionToggle(_:isSuppressed:)**: Enables user suppression of dialogs and alerts presented within `self`, with a custom suppression message on macOS. Unused on other platforms.
- **dialogSuppressionToggle(_:isSuppressed:)**: Enables user suppression of an alert with a custom suppression message.

## Exporting to file

- **fileExporter(isPresented:document:contentType:defaultFilename:onCompletion:)**: Presents a system interface for exporting a document that’s stored in a value type, like a structure, to a file on disk.
- **fileExporter(isPresented:documents:contentType:onCompletion:)**: Presents a system interface for exporting a collection of value type documents to files on disk.
- **fileExporter(isPresented:document:contentTypes:defaultFilename:onCompletion:onCancellation:)**: Presents a system interface for allowing the user to export a `FileDocument` to a file on disk.
- **fileExporter(isPresented:documents:contentTypes:onCompletion:onCancellation:)**: Presents a system dialog for allowing the user to export a collection of documents that conform to `FileDocument` to files on disk.
- **fileExporter(isPresented:item:contentTypes:defaultFilename:onCompletion:onCancellation:)**: Presents a system interface allowing the user to export a `Transferable` item to file on disk.
- **fileExporter(isPresented:items:contentTypes:onCompletion:onCancellation:)**: Presents a system interface allowing the user to export a collection of items to files on disk.
- **fileExporterFilenameLabel(_:)**: On macOS, configures the `fileExporter` with a label for the file name field.

## Importing from file

- **fileImporter(isPresented:allowedContentTypes:allowsMultipleSelection:onCompletion:)**: Presents a system interface for allowing the user to import multiple files.
- **fileImporter(isPresented:allowedContentTypes:onCompletion:)**: Presents a system interface for allowing the user to import an existing file.
- **fileImporter(isPresented:allowedContentTypes:allowsMultipleSelection:onCompletion:onCancellation:)**: Presents a system dialog for allowing the user to import multiple files.

## Moving a file

- **fileMover(isPresented:file:onCompletion:)**: Presents a system interface for allowing the user to move an existing file to a new location.
- **fileMover(isPresented:files:onCompletion:)**: Presents a system interface for allowing the user to move a collection of existing files to a new location.
- **fileMover(isPresented:file:onCompletion:onCancellation:)**: Presents a system dialog for allowing the user to move an existing file to a new location.
- **fileMover(isPresented:files:onCompletion:onCancellation:)**: Presents a system dialog for allowing the user to move a collection of existing files to a new location.

## Configuring a file dialog

- **fileDialogBrowserOptions(_:)**: On macOS, configures the `fileExporter`, `fileImporter`, or `fileMover` to provide a refined URL search experience: include or exclude hidden files, allow searching by tag, etc.
- **fileDialogConfirmationLabel(_:)**: On macOS, configures the `fileExporter`, `fileImporter`, or `fileMover` with a custom confirmation button label.
- **fileDialogCustomizationID(_:)**: On macOS, configures the `fileExporter`, `fileImporter`, or `fileMover` to persist and restore the file dialog configuration.
- **fileDialogDefaultDirectory(_:)**: Configures the `fileExporter`, `fileImporter`, or `fileMover` to open with the specified default directory.
- **fileDialogImportsUnresolvedAliases(_:)**: On macOS, configures the `fileExporter`, `fileImporter`, or `fileMover` behavior when a user chooses an alias.
- **fileDialogMessage(_:)**: On macOS, configures the `fileExporter`, `fileImporter`, or `fileMover` with a custom text that is presented to the user, similar to a title.
- **fileDialogURLEnabled(_:)**: On macOS, configures the `fileImporter` or `fileMover` to conditionally disable presented URLs.
- **FileDialogBrowserOptions**: The way that file dialogs present the file system.

## Presenting an inspector

- **inspector(isPresented:content:)**: Inserts an inspector at the applied position in the view hierarchy.
- **inspectorColumnWidth(_:)**: Sets a fixed, preferred width for the inspector containing this view when presented as a trailing column.
- **inspectorColumnWidth(min:ideal:max:)**: Sets a flexible, preferred width for the inspector in a trailing-column presentation.

## Dismissing a presentation

- **isPresented**: A Boolean value that indicates whether the view associated with this environment is currently presented.
- **dismiss**: An action that dismisses the current presentation.
- **DismissAction**: An action that dismisses a presentation.
- **interactiveDismissDisabled(_:)**: Conditionally prevents interactive dismissal of presentations like popovers, sheets, and inspectors.

## Deprecated modal presentations

- **Alert**: A representation of an alert presentation.
- **ActionSheet**: A representation of an action sheet presentation.

## App structure

- **App organization**: Define the entry point and top-level structure of your app.
- **Scenes**: Declare the user interface groupings that make up the parts of your app.
- **Windows**: Display user interface content in a window or a collection of windows.
- **Immersive spaces**: Display unbounded content in a person’s surroundings.
- **Documents**: Enable people to open and manage documents.
- **Navigation**: Enable people to move between different parts of your app’s view hierarchy within a scene.
- **Toolbars**: Provide immediate access to frequently used commands and controls.
- **Search**: Enable people to search for text or other content within your app.
- **App extensions**: Extend your app’s basic functionality to other parts of the system, like by adding a Widget.

