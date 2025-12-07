--- 来源：https://developer.apple.com/documentation/SwiftUI/View/onCutCommand(perform:)

抓取时间：2025-11-30T21:27:41Z

---

# onCutCommand(perform:)

**实例方法**

添加一个操作，用于响应系统的剪切命令。

## 声明

```swift
nonisolated func onCutCommand(perform payloadAction: (() -> [NSItemProvider])?) -> some View

```

## 参数

- **payloadAction**：一个操作闭包，用于删除选定的数据并返回与该数据对应的 [doc://com.apple.documentation/documentation/Foundation/NSItemProvider] 项，这些项应写入剪贴板。如果 `action` 为 `nil`，则剪切命令被视为已禁用。

## 返回值

当系统执行“剪切”命令时，会触发 `action` 的视图。

## 使用项目提供程序复制项目

- **onCopyCommand(perform:)**：添加一个响应系统“复制”命令的操作。

- **onPasteCommand(of:perform:)**：添加一个响应系统“粘贴”命令的操作。

- **onPasteCommand(of:validator:perform:)**：添加一个响应系统“粘贴”命令的操作，该操作适用于您已验证的项目。


---
source: https://developer.apple.com/documentation/SwiftUI/View/onCutCommand(perform:)
crawled: 2025-11-30T21:27:41Z
---

# onCutCommand(perform:)

**Instance Method**

Adds an action to perform in response to the system’s Cut command.

## Declaration

```swift
nonisolated func onCutCommand(perform payloadAction: (() -> [NSItemProvider])?) -> some View

```

## Parameters

- **payloadAction**: An action closure that should delete the selected data and return [doc://com.apple.documentation/documentation/Foundation/NSItemProvider] items corresponding to that data, which should be written to the Clipboard. If `action` is `nil`, the Cut command is considered disabled.

## Return Value

A view that triggers `action` when a system Cut command occurs.

## Copying items using item providers

- **onCopyCommand(perform:)**: Adds an action to perform in response to the system’s Copy command.
- **onPasteCommand(of:perform:)**: Adds an action to perform in response to the system’s Paste command.
- **onPasteCommand(of:validator:perform:)**: Adds an action to perform in response to the system’s Paste command with items that you validate.

