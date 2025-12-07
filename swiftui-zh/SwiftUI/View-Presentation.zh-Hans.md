--- 来源：https://developer.apple.com/documentation/SwiftUI/View-Presentation
抓取时间：2025-12-02T17:22:18Z

---

# 演示修饰符

**API 集合**

定义在特定条件下要显示的附加视图。

## 概述

使用演示修饰符来显示不同类型的模态视图，例如警告框、弹出框、表单和确认对话框。

由于 SwiftUI 是一个声明式框架，因此您无需在想要显示模态视图时调用方法。相反，您需要定义模态视图的外观以及 SwiftUI 应该显示它的条件。SwiftUI 会检测条件何时发生变化并自动进行显示。由于您为启动显示的条件提供了一个 [Binding](Binding.zh-Hans.md)，因此当用户关闭模态视图时，SwiftUI 可以重置底层值。

有关如何使用这些修饰符的更多信息，请参阅 [Modal-presentations](Modal-presentations.zh-Hans.md)。

## 警报

- **alert(_:isPresented:actions:)**：当给定条件为真时，显示警报，标题使用文本视图。

- **alert(_:isPresented:presenting:actions:)**：使用给定数据生成警报内容，并使用文本视图作为标题。

- **alert(isPresented:error:actions:)**：当出现错误时，显示警报。

## 带消息的警报

- **alert(_:isPresented:actions:message:)**：当给定条件为真时，显示带有消息的警报，标题使用文本视图。

- **alert(_:isPresented:presenting:actions:message:)**：使用给定数据生成警报内容，并使用文本视图作为标题，显示带有消息的警报。

- **alert(isPresented:error:actions:message:)**：出现错误时显示带有消息的警告。

## 确认对话框

- **confirmationDialog(_:isPresented:titleVisibility:actions:)**：当满足给定条件时，显示一个确认对话框，标题使用文本视图。

- **confirmationDialog(_:isPresented:titleVisibility:presenting:actions:)**：显示一个确认对话框，对话框内容由数据生成，标题使用文本视图。

- **dismissalConfirmationDialog(_:shouldPresent:actions:)**：当触发关闭操作时，显示一个确认对话框。

## 带有消息的确认对话框

- **confirmationDialog(_:isPresented:titleVisibility:actions:message:)**：当满足给定条件时，显示一个带有消息的确认对话框，标题使用文本视图。

- **confirmationDialog(_:isPresented:titleVisibility:presenting:actions:message:)**：显示一个带有消息的确认对话框，对话框内容由数据生成，消息使用文本视图。

- **dismissalConfirmationDialog(_:shouldPresent:actions:message:)**：当触发关闭操作时，显示确认对话框。

## 对话框配置

- **dialogIcon(_:)**：配置此视图中对话框使用的图标。

- **dialogSeverity(_:)**

- **dialogSuppressionToggle(isSuppressed:)**：允许用户屏蔽 `self` 中显示的对话框和警告，macOS 系统上会显示默认的屏蔽消息。其他平台未使用此功能。

- **dialogSuppressionToggle(_:isSuppressed:)**：允许用户屏蔽 `self` 中显示的对话框和警告，macOS 系统上会显示自定义的屏蔽消息。其他平台未使用此功能。

## 工作表

- **sheet(isPresented:onDismiss:content:)**：当您提供的布尔值绑定为真时，显示工作表。

- **sheet(item:onDismiss:content:)**：使用指定项作为工作表内容的数据源，显示一个工作表。

- **fullScreenCover(isPresented:onDismiss:content:)**：当绑定到您提供的布尔值且该值为真时，显示一个尽可能覆盖屏幕的模态视图。

- **fullScreenCover(item:onDismiss:content:)**：使用您提供的绑定作为工作表内容的数据源，显示一个尽可能覆盖屏幕的模态视图。

## 弹出框

- **popover(item:attachmentAnchor:arrowEdge:content:)**：使用指定项作为弹出框内容的数据源，显示一个弹出框。

- **popover(isPresented:attachmentAnchor:arrowEdge:content:)**：当给定条件为真时，显示一个弹出框。

## 工作表和弹出框配置

- **interactiveDismissDisabled(_:)**：有条件地阻止交互式关闭弹出框、工作表和检查器等演示。

- **presentationDetents(_:)**：设置包含工作表的可用位置。

- **presentationDetents(_:selection:)**：设置包含工作表的可用位置，允许您以编程方式控制当前选定的位置。

- **presentationDragIndicator(_:)**：设置工作表顶部拖动指示器的可见性。

- **presentationBackground(_:)**：使用形状样式设置包含工作表的演示背景。

- **presentationBackground(alignment:content:)**：将包含工作表的演示背景设置为自定义视图。

- **presentationBackgroundInteraction(_:)**：控制用户是否可以与演示文稿背后的视图进行交互。

- **presentationCompactAdaptation(horizontal:vertical:)**：指定如何将演示文稿调整为水平和垂直方向的紧凑尺寸类别。

- **presentationCompactAdaptation(_:)**：指定如何将演示文稿调整为紧凑尺寸类别。

- **presentationContentInteraction(_:)**：配置演示文稿上的滑动操作行为。

- **presentationCornerRadius(_:)**：请求演示文稿具有特定的圆角半径。

- **presentationSizing(_:)**：设置包含演示文稿的尺寸。

## 文件导出器

- **fileExporter(isPresented:document:contentType:defaultFilename:onCompletion:)**：提供一个系统接口，用于将存储在值类型（例如结构体）中的文档导出到磁盘上的文件。

- **fileExporter(isPresented:documents:contentType:onCompletion:)**：提供一个系统界面，用于将值类型文档集合导出到磁盘上的文件。

- **fileExporter(isPresented:document:contentTypes:defaultFilename:onCompletion:onCancellation:)**：提供一个系统界面，允许用户将 `FileDocument` 导出到磁盘上的文件。

- **fileExporter(isPresented:documents:contentTypes:onCompletion:onCancellation:)**：提供一个系统对话框，允许用户将符合 `FileDocument` 的文档集合导出到磁盘上的文件。

- **fileExporter(isPresented:item:contentTypes:defaultFilename:onCompletion:onCancellation:)**：提供一个系统界面，允许用户将 `Transferable` 项目导出到磁盘上的文件。

- **fileExporter(isPresented:items:contentTypes:onCompletion:onCancellation:)**：提供一个系统界面，允许用户将项目集合导出到磁盘上的文件。

- **fileExporterFilenameLabel(_:)**：在 macOS 系统中，为 `fileExporter` 的文件名字段配置标签。

## 文件导入器

- **fileImporter(isPresented:allowedContentTypes:allowsMultipleSelection:onCompletion:)**：提供一个系统界面，允许用户导入多个文件。

- **fileImporter(isPresented:allowedContentTypes:onCompletion:)**：提供一个系统界面，允许用户导入现有文件。

- **fileImporter(isPresented:allowedContentTypes:allowsMultipleSelection:onCompletion:onCancellation:)**：提供一个系统对话框，允许用户导入多个文件。

## 文件移动器

- **fileMover(isPresented:file:onCompletion:)**：提供一个系统界面，允许用户将现有文件移动到新位置。

- **fileMover(isPresented:files:onCompletion:)**：提供一个系统界面，允许用户将多个现有文件移动到新位置。

- **fileMover(isPresented:file:onCompletion:onCancellation:)**：显示一个系统对话框，允许用户将现有文件移动到新位置。

- **fileMover(isPresented:files:onCompletion:onCancellation:)**：显示一个系统对话框，允许用户将一组现有文件移动到新位置。

## 文件对话框配置

- **fileDialogBrowserOptions(_:)**：在 macOS 上，配置 `fileExporter`、`fileImporter` 或 `fileMover`，以提供更完善的 URL 搜索体验：包含或排除隐藏文件、允许按标签搜索等。

- **fileDialogConfirmationLabel(_:)**：在 macOS 上，配置 `fileExporter`、`fileImporter` 或 `fileMover`，为其添加自定义确认按钮标签。

- **fileDialogCustomizationID(_:)**：在 macOS 系统上，配置 `fileExporter`、`fileImporter` 或 `fileMover` 以持久化和恢复文件对话框配置。

- **fileDialogDefaultDirectory(_:)**：配置 `fileExporter`、`fileImporter` 或 `fileMover` 以使用指定的默认目录打开文件。

- **fileDialogImportsUnresolvedAliases(_:)**：在 macOS 系统上，配置 `fileExporter`、`fileImporter` 或 `fileMover` 在用户选择别名时的行为。

- **fileDialogMessage(_:)**：在 macOS 系统中，配置 `fileExporter`、`fileImporter` 或 `fileMover`，使其显示类似标题的自定义文本。

- **fileDialogURLEnabled(_:)**：在 macOS 系统中，配置 `fileImporter` 或 `fileMover`，使其在特定条件下禁用显示的 URL。

## 检查器

- **inspector(isPresented:content:)**：在视图层级结构中的指定位置插入一个检查器。

- **inspectorColumnWidth(_:)**：设置当此视图的检查器作为尾随列显示时，其固定的首选宽度。

- **inspectorColumnWidth(min:ideal:max:)**：设置检查器在后列显示模式下的灵活首选宽度。

## 快速预览

- **quickLookPreview(_:)**：显示单个 URL 内容的快速预览。

- **quickLookPreview(_:in:)**：显示您提供的 URL 的快速预览。

## 家庭共享

- **familyActivityPicker(isPresented:selection:)**：将活动选择器视图显示为工作表。

- **familyActivityPicker(headerText:footerText:isPresented:selection:)**：将活动选择器视图显示为工作表。

## 实时活动

- **activitySystemActionForegroundColor(_:)**：系统在锁定屏幕上显示的实时活动旁边的辅助操作按钮的文本颜色。

- **activityBackgroundTint(_:)**：设置锁定屏幕上显示的 Live Activity 的背景色调。

## Apple Music

- **musicSubscriptionOffer(isPresented:options:onLoadCompletion:)**：当 `isPresented` 绑定为 `true` 时，启动显示 Apple Music 订阅优惠的流程。

## StoreKit

- **appStoreOverlay(isPresented:configuration:)**：当满足给定条件时，显示 StoreKit 叠加层。

- **manageSubscriptionsSheet(isPresented:)**

- **refundRequestSheet(for:isPresented:onDismiss:)**：显示指定交易的退款申请表单。

- **offerCodeRedemption(isPresented:onCompletion:)**：显示一个表单，允许客户兑换您在 App Store Connect 中配置的优惠码。

## 照片套件

- **photosPicker(isPresented:selection:matching:preferredItemEncoding:)**：显示一个照片选择器，用于选择 `PhotosPickerItem`。

- **photosPicker(isPresented:selection:matching:preferredItemEncoding:photoLibrary:)**：显示一个照片选择器，用于从指定的照片库中选择 `PhotosPickerItem`。

- **photosPicker(isPresented:selection:maxSelectionCount:selectionBehavior:matching:preferredItemEncoding:)**：显示一个照片选择器，用于选择 `PhotosPickerItem` 的集合。

- **photosPicker(isPresented:selection:maxSelectionCount:selectionBehavior:matching:preferredItemEncoding:photoLibrary:)**：显示一个照片选择器，用于从指定的照片库中选择 `PhotosPickerItem` 的集合。

- **photosPickerAccessoryVisibility(_:edges:)**：设置照片选择器的辅助元素可见性。辅助元素包括内容和边缘之间的任何元素，例如导航栏或侧边栏。

- **photosPickerDisabledCapabilities(_:)**：禁用照片选择器的功能。

- **photosPickerStyle(_:)**：设置照片选择器的模式。

## 提供交互功能

- **输入和事件修饰符**：为视图提供响应用户输入和系统事件的操作。

- **搜索修饰符**：使用户能够在您的应用中搜索内容。

- **状态修饰符**：访问存储并为子视图提供配置数据。


---
source: https://developer.apple.com/documentation/SwiftUI/View-Presentation
crawled: 2025-12-02T17:22:18Z
---

# Presentation modifiers

**API Collection**

Define additional views for the view to present under specified conditions.

## Overview

Use presentation modifiers to show different kinds of modal presentations, like alerts, popovers, sheets, and confirmation dialogs.

Because SwiftUI is a declarative framework, you don’t call a method at the moment you want to present the modal. Rather, you define how the presentation looks and the condition under which SwiftUI should present it. SwiftUI detects when the condition changes and makes the presentation for you. Because you provide a [Binding](Binding.zh-Hans.md) to the condition that initiates the presentation, SwiftUI can reset the underlying value when the user dismisses the presentation.

For more information about how to use these modifiers, see [Modal-presentations](Modal-presentations.zh-Hans.md).

## Alerts

- **alert(_:isPresented:actions:)**: Presents an alert when a given condition is true, using a text view for the title.
- **alert(_:isPresented:presenting:actions:)**: Presents an alert using the given data to produce the alert’s content and a text view as a title.
- **alert(isPresented:error:actions:)**: Presents an alert when an error is present.

## Alerts with a message

- **alert(_:isPresented:actions:message:)**: Presents an alert with a message when a given condition is true using a text view as a title.
- **alert(_:isPresented:presenting:actions:message:)**: Presents an alert with a message using the given data to produce the alert’s content and a text view for a title.
- **alert(isPresented:error:actions:message:)**: Presents an alert with a message when an error is present.

## Confirmation dialogs

- **confirmationDialog(_:isPresented:titleVisibility:actions:)**: Presents a confirmation dialog when a given condition is true, using a text view for the title.
- **confirmationDialog(_:isPresented:titleVisibility:presenting:actions:)**: Presents a confirmation dialog using data to produce the dialog’s content and a text view for the title.
- **dismissalConfirmationDialog(_:shouldPresent:actions:)**: Presents a confirmation dialog when a dismiss action has been triggered.

## Confirmation dialogs with a message

- **confirmationDialog(_:isPresented:titleVisibility:actions:message:)**: Presents a confirmation dialog with a message when a given condition is true, using a text view for the title.
- **confirmationDialog(_:isPresented:titleVisibility:presenting:actions:message:)**: Presents a confirmation dialog with a message using data to produce the dialog’s content and a text view for the message.
- **dismissalConfirmationDialog(_:shouldPresent:actions:message:)**: Presents a confirmation dialog when a dismiss action has been triggered.

## Dialog configuration

- **dialogIcon(_:)**: Configures the icon used by dialogs within this view.
- **dialogSeverity(_:)**
- **dialogSuppressionToggle(isSuppressed:)**: Enables user suppression of dialogs and alerts presented within `self`, with a default suppression message on macOS. Unused on other platforms.
- **dialogSuppressionToggle(_:isSuppressed:)**: Enables user suppression of dialogs and alerts presented within `self`, with a custom suppression message on macOS. Unused on other platforms.

## Sheets

- **sheet(isPresented:onDismiss:content:)**: Presents a sheet when a binding to a Boolean value that you provide is true.
- **sheet(item:onDismiss:content:)**: Presents a sheet using the given item as a data source for the sheet’s content.
- **fullScreenCover(isPresented:onDismiss:content:)**: Presents a modal view that covers as much of the screen as possible when binding to a Boolean value you provide is true.
- **fullScreenCover(item:onDismiss:content:)**: Presents a modal view that covers as much of the screen as possible using the binding you provide as a data source for the sheet’s content.

## Popovers

- **popover(item:attachmentAnchor:arrowEdge:content:)**: Presents a popover using the given item as a data source for the popover’s content.
- **popover(isPresented:attachmentAnchor:arrowEdge:content:)**: Presents a popover when a given condition is true.

## Sheet and popover configuration

- **interactiveDismissDisabled(_:)**: Conditionally prevents interactive dismissal of presentations like popovers, sheets, and inspectors.
- **presentationDetents(_:)**: Sets the available detents for the enclosing sheet.
- **presentationDetents(_:selection:)**: Sets the available detents for the enclosing sheet, giving you programmatic control of the currently selected detent.
- **presentationDragIndicator(_:)**: Sets the visibility of the drag indicator on top of a sheet.
- **presentationBackground(_:)**: Sets the presentation background of the enclosing sheet using a shape style.
- **presentationBackground(alignment:content:)**: Sets the presentation background of the enclosing sheet to a custom view.
- **presentationBackgroundInteraction(_:)**: Controls whether people can interact with the view behind a presentation.
- **presentationCompactAdaptation(horizontal:vertical:)**: Specifies how to adapt a presentation to horizontally and vertically compact size classes.
- **presentationCompactAdaptation(_:)**: Specifies how to adapt a presentation to compact size classes.
- **presentationContentInteraction(_:)**: Configures the behavior of swipe gestures on a presentation.
- **presentationCornerRadius(_:)**: Requests that the presentation have a specific corner radius.
- **presentationSizing(_:)**: Sets the sizing of the containing presentation.

## File exporter

- **fileExporter(isPresented:document:contentType:defaultFilename:onCompletion:)**: Presents a system interface for exporting a document that’s stored in a value type, like a structure, to a file on disk.
- **fileExporter(isPresented:documents:contentType:onCompletion:)**: Presents a system interface for exporting a collection of value type documents to files on disk.
- **fileExporter(isPresented:document:contentTypes:defaultFilename:onCompletion:onCancellation:)**: Presents a system interface for allowing the user to export a `FileDocument` to a file on disk.
- **fileExporter(isPresented:documents:contentTypes:onCompletion:onCancellation:)**: Presents a system dialog for allowing the user to export a collection of documents that conform to `FileDocument` to files on disk.
- **fileExporter(isPresented:item:contentTypes:defaultFilename:onCompletion:onCancellation:)**: Presents a system interface allowing the user to export a `Transferable` item to file on disk.
- **fileExporter(isPresented:items:contentTypes:onCompletion:onCancellation:)**: Presents a system interface allowing the user to export a collection of items to files on disk.
- **fileExporterFilenameLabel(_:)**: On macOS, configures the `fileExporter` with a label for the file name field.

## File importer

- **fileImporter(isPresented:allowedContentTypes:allowsMultipleSelection:onCompletion:)**: Presents a system interface for allowing the user to import multiple files.
- **fileImporter(isPresented:allowedContentTypes:onCompletion:)**: Presents a system interface for allowing the user to import an existing file.
- **fileImporter(isPresented:allowedContentTypes:allowsMultipleSelection:onCompletion:onCancellation:)**: Presents a system dialog for allowing the user to import multiple files.

## File mover

- **fileMover(isPresented:file:onCompletion:)**: Presents a system interface for allowing the user to move an existing file to a new location.
- **fileMover(isPresented:files:onCompletion:)**: Presents a system interface for allowing the user to move a collection of existing files to a new location.
- **fileMover(isPresented:file:onCompletion:onCancellation:)**: Presents a system dialog for allowing the user to move an existing file to a new location.
- **fileMover(isPresented:files:onCompletion:onCancellation:)**: Presents a system dialog for allowing the user to move a collection of existing files to a new location.

## File dialog configuration

- **fileDialogBrowserOptions(_:)**: On macOS, configures the `fileExporter`, `fileImporter`, or `fileMover` to provide a refined URL search experience: include or exclude hidden files, allow searching by tag, etc.
- **fileDialogConfirmationLabel(_:)**: On macOS, configures the `fileExporter`, `fileImporter`, or `fileMover` with a custom confirmation button label.
- **fileDialogCustomizationID(_:)**: On macOS, configures the `fileExporter`, `fileImporter`, or `fileMover` to persist and restore the file dialog configuration.
- **fileDialogDefaultDirectory(_:)**: Configures the `fileExporter`, `fileImporter`, or `fileMover` to open with the specified default directory.
- **fileDialogImportsUnresolvedAliases(_:)**: On macOS, configures the `fileExporter`, `fileImporter`, or `fileMover` behavior when a user chooses an alias.
- **fileDialogMessage(_:)**: On macOS, configures the `fileExporter`, `fileImporter`, or `fileMover` with a custom text that is presented to the user, similar to a title.
- **fileDialogURLEnabled(_:)**: On macOS, configures the `fileImporter` or `fileMover` to conditionally disable presented URLs.

## Inspectors

- **inspector(isPresented:content:)**: Inserts an inspector at the applied position in the view hierarchy.
- **inspectorColumnWidth(_:)**: Sets a fixed, preferred width for the inspector containing this view when presented as a trailing column.
- **inspectorColumnWidth(min:ideal:max:)**: Sets a flexible, preferred width for the inspector in a trailing-column presentation.

## Quick look previews

- **quickLookPreview(_:)**: Presents a Quick Look preview of the contents of a single URL.
- **quickLookPreview(_:in:)**: Presents a Quick Look preview of the URLs you provide.

## Family Sharing

- **familyActivityPicker(isPresented:selection:)**: Presents an activity picker view as a sheet.
- **familyActivityPicker(headerText:footerText:isPresented:selection:)**: Presents an activity picker view as a sheet.

## Live Activities

- **activitySystemActionForegroundColor(_:)**: The text color for the auxiliary action button that the system shows next to a Live Activity on the Lock Screen.
- **activityBackgroundTint(_:)**: Sets the tint color for the background of a Live Activity that appears on the Lock Screen.

## Apple Music

- **musicSubscriptionOffer(isPresented:options:onLoadCompletion:)**: Initiates the process of presenting a sheet with subscription offers for Apple Music when the `isPresented` binding is `true`.

## StoreKit

- **appStoreOverlay(isPresented:configuration:)**: Presents a StoreKit overlay when a given condition is true.
- **manageSubscriptionsSheet(isPresented:)**
- **refundRequestSheet(for:isPresented:onDismiss:)**: Display the refund request sheet for the given transaction.
- **offerCodeRedemption(isPresented:onCompletion:)**: Presents a sheet that enables customers to redeem offer codes that you configure in App Store Connect.

## PhotoKit

- **photosPicker(isPresented:selection:matching:preferredItemEncoding:)**: Presents a Photos picker that selects a `PhotosPickerItem`.
- **photosPicker(isPresented:selection:matching:preferredItemEncoding:photoLibrary:)**: Presents a Photos picker that selects a `PhotosPickerItem` from a given photo library.
- **photosPicker(isPresented:selection:maxSelectionCount:selectionBehavior:matching:preferredItemEncoding:)**: Presents a Photos picker that selects a collection of `PhotosPickerItem`.
- **photosPicker(isPresented:selection:maxSelectionCount:selectionBehavior:matching:preferredItemEncoding:photoLibrary:)**: Presents a Photos picker that selects a collection of `PhotosPickerItem` from a given photo library.
- **photosPickerAccessoryVisibility(_:edges:)**: Sets the accessory visibility of the Photos picker. Accessories include anything between the content and the edge, like the navigation bar or the sidebar.
- **photosPickerDisabledCapabilities(_:)**: Disables capabilities of the Photos picker.
- **photosPickerStyle(_:)**: Sets the mode of the Photos picker.

## Providing interactivity

- **Input and event modifiers**: Supply actions for a view to perform in response to user input and system events.
- **Search modifiers**: Enable people to search for content in your app.
- **State modifiers**: Access storage and provide child views with configuration data.

