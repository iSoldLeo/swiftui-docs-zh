--- 来源：https://developer.apple.com/documentation/SwiftUI/View/cuttable(for:action:)

抓取时间：2025-12-02T17:42:34Z

---

# cuttable(for:action:)

**实例方法**

指定一个操作，该操作响应系统的“剪切”命令将项目移动到剪贴板。

## 声明

```swift
nonisolated func cuttable<T>(for payloadType: T.Type = T.self, action: @escaping () -> [T]) -> some View where T : Transferable

```

## 参数

- **payloadType**：要剪切的项目类型。

- **action**：一个闭包，用于从集合中删除选定的项目，并将它们返回以添加到剪贴板。这些项目必须符合 [doc://com.apple.documentation/documentation/CoreTransferable/Transferable] 协议。

## 返回值

一个视图，该视图响应“剪切”命令将一个或多个项目发送到剪贴板。

## 讨论

使用此修饰符可以从项目集合中移除一个或多个项目，并在用户发出“剪切”命令时将这些项目移动到剪贴板。用户可以通过从应用菜单中选择“编辑”>“剪切”或使用快捷键 Command-X 来发出“剪切”命令。当系统检测到可剪切的内容时，会为您的应用启用“剪切”命令。

例如，以下代码允许用户从鸟类列表中移除鸟类名称：

```swift
struct CuttableExample: View {
    @State private var birds = ["owl", "parrot", "swift"]
    @State private var selection: Set<String> = []

    var body: some View {
        List(birds, id: \.self, selection: $selection) {
            Text($0)
        }
        .cuttable(for: String.self) {
            for bird in selection {
                birds.removeAll(where: { $0 == bird })
            }
            return Array(selection)
        }
    }
}
```

当用户选择“猫头鹰”并发出“剪切”命令时，`action` 闭包会从列表中移除所选项目并将其返回。作为响应，SwiftUI 会将其移动到剪贴板。如果要复制项目而不移除它，请改用 [copyable(_:)](copyable.zh-Hans.md) 修饰符。

## 复制可转移项目

- **copyable(_:)**：指定要响应系统“复制”命令而复制的项目列表。 - **pasteDestination(for:action:validator:)**：指定响应系统“粘贴”命令而将已验证的项目添加到视图中的操作。


---
source: https://developer.apple.com/documentation/SwiftUI/View/cuttable(for:action:)
crawled: 2025-12-02T17:42:34Z
---

# cuttable(for:action:)

**Instance Method**

Specifies an action that moves items to the Clipboard in response to the system’s Cut command.

## Declaration

```swift
nonisolated func cuttable<T>(for payloadType: T.Type = T.self, action: @escaping () -> [T]) -> some View where T : Transferable

```

## Parameters

- **payloadType**: The type of items to cut.
- **action**: A closure that you implement to delete the selected items from the collection, and return them for addition to the Clipboard. The items must conform to the [doc://com.apple.documentation/documentation/CoreTransferable/Transferable] protocol.

## Return Value

A view that sends one or more items to the Clipboard in response to a Cut command.

## Discussion

Use this modifier to remove one or more items from a collection of items and then move the items to the Clipboard when someone issues a Cut command. People issue a Cut command by choosing Edit > Cut from the app’s menu, or by using the Command-X keyboard shortcut. The system enables the Cut command for your app when it detects cuttable content.

For example, the following code enables people to remove bird names from a list of birds:

```swift
struct CuttableExample: View {
    @State private var birds = ["owl", "parrot", "swift"]
    @State private var selection: Set<String> = []

    var body: some View {
        List(birds, id: \.self, selection: $selection) {
            Text($0)
        }
        .cuttable(for: String.self) {
            for bird in selection {
                birds.removeAll(where: { $0 == bird })
            }
            return Array(selection)
        }
    }
}
```

When someone selects “owl” and issues a Cut command, the `action` closure removes the selected item from the list and returns it. In response, SwiftUI moves it to the Clipboard. If you want to copy the item without removing it, use the [copyable(_:)](copyable.zh-Hans.md) modifier instead.



## Copying transferable items

- **copyable(_:)**: Specifies a list of items to copy in response to the system’s Copy command.
- **pasteDestination(for:action:validator:)**: Specifies an action that adds validated items to a view in response to the system’s Paste command.

