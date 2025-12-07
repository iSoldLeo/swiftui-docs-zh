--- 来源：https://developer.apple.com/documentation/SwiftUI/View/onPasteCommand(of:validator:perform:)

抓取时间：2025-12-02T17:42:37Z

---

# onPasteCommand(of:validator:perform:)

**实例方法**

添加一个操作，用于响应系统的粘贴命令，并验证粘贴的内容。

## 声明

```swift
nonisolated func onPasteCommand<Payload>(of supportedContentTypes: [UTType], validator: @escaping ([NSItemProvider]) -> Payload?, perform payloadAction: @escaping (Payload) -> Void) -> some View

```

## 参数

- **supportedContentTypes**：描述此视图可通过粘贴操作接收的内容类型的统一类型标识符。如果剪贴板不包含任何受支持的类型，则不会触发粘贴命令。

- **validator**：用于验证命令的处理程序。此处理程序从剪贴板接收您在 `supportedContentTypes` 中指定的类型的项目。使用此处理程序判断项目是否有效，并对其进行预处理，以便用于 `action` 闭包。如果您返回 `nil`，则不会触发粘贴命令。

- **payloadAction**：粘贴命令触发时要执行的操作。

## 返回值

一个视图，当系统调用粘贴命令时，该视图会触发 `action`，并使用 `validator` 验证粘贴命令。

## 说明

将统一类型标识符数组传递给 `supportedContentTypes` 参数。将优先级较高的类型放在数组的开头附近。 `validator` 闭包接收到的剪贴板项，其类型为源支持的所有类型中最优先的类型。

例如，如果您的应用可以处理纯文本和富文本，但您更倾向于富文本，请将富文本类型放在数组的首位。如果粘贴操作发生时富文本可用，`validator` 闭包会将该富文本传递下去。

## 使用项目提供程序复制项目

- **onCopyCommand(perform:)**：添加一个响应系统“复制”命令的操作。

- **onCutCommand(perform:)**：添加一个响应系统“剪切”命令的操作。

- **onPasteCommand(of:perform:)**：添加一个响应系统“粘贴”命令的操作。


---
source: https://developer.apple.com/documentation/SwiftUI/View/onPasteCommand(of:validator:perform:)
crawled: 2025-12-02T17:42:37Z
---

# onPasteCommand(of:validator:perform:)

**Instance Method**

Adds an action to perform in response to the system’s Paste command with items that you validate.

## Declaration

```swift
nonisolated func onPasteCommand<Payload>(of supportedContentTypes: [UTType], validator: @escaping ([NSItemProvider]) -> Payload?, perform payloadAction: @escaping (Payload) -> Void) -> some View

```

## Parameters

- **supportedContentTypes**: The uniform type identifiers that describe the types of content this view can accept through a paste action. If the Clipboard doesn’t contain any of the supported types, the Paste command doesn’t trigger.
- **validator**: A handler that validates the command. This handler receives items from the Clipboard with the types you specify in the `supportedContentTypes`. Use this handler to decide whether the items are valid and preprocess them for the `action` closure. If you return `nil` instead, the Paste command doesn’t trigger.
- **payloadAction**: The action to perform when the Paste command triggers.

## Return Value

A view that triggers `action` when the system Paste command is invoked, validating the Paste command with `validator`.

## Discussion

Pass an array of uniform type identifiers to the `supportedContentTypes` parameter. Place the higher priority types closer to the beginning of the array. The Clipboard items that the `validator` closure receives have the most preferred type out of all the types the source supports.

For example, if your app can handle plain text and rich text, but you prefer rich text, place the rich text type first in the array. If rich text is available when the paste action occurs, the `validator` closure passes that rich text along.

## Copying items using item providers

- **onCopyCommand(perform:)**: Adds an action to perform in response to the system’s Copy command.
- **onCutCommand(perform:)**: Adds an action to perform in response to the system’s Cut command.
- **onPasteCommand(of:perform:)**: Adds an action to perform in response to the system’s Paste command.

