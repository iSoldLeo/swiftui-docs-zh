--- 来源：https://developer.apple.com/documentation/SwiftUI/View/onPasteCommand(of:perform:)-4f78f

抓取时间：2025-12-01T10:24:58Z

---

# onPasteCommand(of:perform:)

**实例方法**

添加一个响应系统粘贴命令而执行的操作。

## 声明

```swift
nonisolated func onPasteCommand(of supportedTypes: [String], perform payloadAction: @escaping ([NSItemProvider]) -> Void) -> some View

```

## 参数

- **supportedTypes**：描述此视图可通过粘贴操作接收的内容类型的统一类型标识符。如果剪贴板不包含任何受支持的类型，则不会触发粘贴命令。

- **payloadAction**：粘贴命令触发时要执行的操作。操作闭包的参数包含剪贴板中的项目，其类型由您在 `supportedTypes` 参数中指定。

## 返回值

当系统执行粘贴命令时，会触发 `action` 的视图。

## 说明

将统一类型标识符数组传递给 `supportedTypes` 参数。将优先级较高的类型放在数组的开头附近。`action` 闭包接收到的剪贴板项目具有源支持的所有类型中优先级最高的类型。

例如，如果您的应用可以处理纯文本和富文本，但您更倾向于富文本，请将富文本类型放在数组的开头。如果在执行粘贴操作时富文本可用，`action` 闭包会传递该富文本。


---
source: https://developer.apple.com/documentation/SwiftUI/View/onPasteCommand(of:perform:)-4f78f
crawled: 2025-12-01T10:24:58Z
---

# onPasteCommand(of:perform:)

**Instance Method**

Adds an action to perform in response to the system’s Paste command.

## Declaration

```swift
nonisolated func onPasteCommand(of supportedTypes: [String], perform payloadAction: @escaping ([NSItemProvider]) -> Void) -> some View

```

## Parameters

- **supportedTypes**: The uniform type identifiers that describe the types of content this view can accept through a paste action. If the Clipboard doesn’t contain any of the supported types, the Paste command doesn’t trigger.
- **payloadAction**: The action to perform when the Paste command triggers. The action closure’s parameter contains items from the Clipboard with the types you specify in the `supportedTypes` parameter.

## Return Value

A view that triggers `action` when a system Paste command occurs.

## Discussion

Pass an array of uniform type identifiers to the `supportedTypes` parameter. Place the higher priority types closer to the beginning of the array. The Clipboard items that the `action` closure receives have the most preferred type out of all the types the source supports.

For example, if your app can handle plain text and rich text, but you prefer rich text, place the rich text type first in the array. If rich text is available when the paste action occurs, the `action` closure passes that rich text along.

