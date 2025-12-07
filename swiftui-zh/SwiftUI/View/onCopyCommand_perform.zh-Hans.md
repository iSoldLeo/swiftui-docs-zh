--- 来源：https://developer.apple.com/documentation/SwiftUI/View/onCopyCommand(perform:)

抓取时间：2025-11-30T21:27:41Z

---

# onCopyCommand(perform:)

**实例方法**

添加一个操作，用于响应系统的复制命令。

## 声明

```swift
nonisolated func onCopyCommand(perform payloadAction: (() -> [NSItemProvider])?) -> some View

```

## 参数

- **payloadAction**：一个操作闭包，返回在触发复制命令时应复制到剪贴板的[doc://com.apple.documentation/documentation/Foundation/NSItemProvider]项。如果`action`为`nil`，则复制命令被视为已禁用。

## 返回值

当系统执行复制命令时，会触发 `action` 的视图。

## 使用项目提供程序复制项目

- **onCutCommand(perform:)**：添加一个操作，用于响应系统的剪切命令。

- **onPasteCommand(of:perform:)**：添加一个操作，用于响应系统的粘贴命令。

- **onPasteCommand(of:validator:perform:)**：添加一个操作，用于响应系统对已验证项目的粘贴命令。


---
source: https://developer.apple.com/documentation/SwiftUI/View/onCopyCommand(perform:)
crawled: 2025-11-30T21:27:41Z
---

# onCopyCommand(perform:)

**Instance Method**

Adds an action to perform in response to the system’s Copy command.

## Declaration

```swift
nonisolated func onCopyCommand(perform payloadAction: (() -> [NSItemProvider])?) -> some View

```

## Parameters

- **payloadAction**: An action closure returning the [doc://com.apple.documentation/documentation/Foundation/NSItemProvider] items that should be copied to the Clipboard when the Copy command is triggered. If `action` is `nil`, the Copy command is considered disabled.

## Return Value

A view that triggers `action` when a system Copy command occurs.

## Copying items using item providers

- **onCutCommand(perform:)**: Adds an action to perform in response to the system’s Cut command.
- **onPasteCommand(of:perform:)**: Adds an action to perform in response to the system’s Paste command.
- **onPasteCommand(of:validator:perform:)**: Adds an action to perform in response to the system’s Paste command with items that you validate.

