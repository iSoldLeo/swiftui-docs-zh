--- 来源：https://developer.apple.com/documentation/SwiftUI/View/copyable(_:)

抓取时间：2025-12-02T17:42:33Z

---

# copyable(_:)

**实例方法**

指定要复制的项目列表，以响应系统的复制命令。

## 声明

```swift
nonisolated func copyable<T>(_ payload: @autoclosure @escaping () -> [T]) -> some View where T : Transferable

```

## 参数

- **payload**：一个闭包，当用户发出复制命令时，返回一个要复制到剪贴板的项目数组。数组中的项目必须符合 [doc://com.apple.documentation/documentation/CoreTransferable/Transferable] 协议。

## 返回值

一个视图，响应复制命令，将一个或多个项目添加到剪贴板。

## 讨论

使用此修饰符可指定一个或多个项目，当用户在修改后的视图获得焦点时发出“复制”命令，系统会将这些项目复制到剪贴板。用户可以通过从应用程序菜单中选择“编辑”>“复制”，或使用快捷键 Command-C 来发出“复制”命令。当系统检测到可复制的内容时，它会为您的应用程序启用“复制”命令。

例如，以下代码允许用户复制他们在 [List](../List.zh-Hans.md) 中选择的所有字符串：

```swift
struct CopyableExample: View {
    let strings = ["Alpha", "Beta", "Gamma"]
    @State private var selection: Set<String> = []

    var body: some View {
        List(strings, id: \.self, selection: $selection) {
            Text($0)
        }
        .copyable(Array(selection))
    }
}
```

该命令会根据每个项目对 [doc://com.apple.documentation/documentation/CoreTransferable/Transferable] 协议的遵循情况，复制每个项目的表示形式。上面的示例使用每个列表项对应的字符串记录选择，而字符串默认遵循 `Transferable` 协议。对于更复杂的情况，您可能需要采取其他步骤。

例如，以下代码显示由包含颜色、名称和标识符的 `Item` 实例列表组成的颜色。该列表使用项目标识符来管理选择：

```swift
struct Item: Identifiable, Transferable {
    let color: Color
    let name: String
    let id = UUID()

    static var transferRepresentation: some TransferRepresentation {
        ProxyRepresentation(exporting: \.name)
    }
}

struct CopyableIDExample: View {
    let items: [Item] = [
        Item(color: .red, name: "red"),
        Item(color: .green, name: "green"),
        Item(color: .blue, name: "blue")
    ]

    @State private var selection: Set<Item.ID> = []

    var body: some View {
        List(items, selection: $selection) { item in
            item.color
        }
        .copyable(items.filter { selection.contains($0.id) })
    }
}
```

此示例执行了前一个示例不需要执行的两项操作：

- 它将选定项目标识符列表转换为选定项目列表，以便与可复制修饰符一起使用。

- 它确保可复制项目符合 [doc://com.apple.documentation/documentation/CoreTransferable/Transferable] 协议，并使用项目的 `name` 属性作为表示。

当用户复制列表中的第一个项目（在界面中显示为红色矩形）并将其粘贴到文本编辑器中时，会得到字符串“red”。

## 复制可转移项目

- **cuttable(for:action:)**：指定响应系统“剪切”命令将项目移动到剪贴板的操作。

- **pasteDestination(for:action:validator:)**：指定响应系统“粘贴”命令将已验证的项目添加到视图的操作。


---
source: https://developer.apple.com/documentation/SwiftUI/View/copyable(_:)
crawled: 2025-12-02T17:42:33Z
---

# copyable(_:)

**Instance Method**

Specifies a list of items to copy in response to the system’s Copy command.

## Declaration

```swift
nonisolated func copyable<T>(_ payload: @autoclosure @escaping () -> [T]) -> some View where T : Transferable

```

## Parameters

- **payload**: A closure that returns an array of items to copy to the Clipboard when someone issues a Copy command. The items in the array must conform to the [doc://com.apple.documentation/documentation/CoreTransferable/Transferable] protocol.

## Return Value

A view that adds one or more items to the Clipboard in response to a Copy command.

## Discussion

Use this modifier to specify one or more items that the system copies to the Clipboard when someone issues a Copy command while the modified view has focus. People issue a Copy command by choosing Edit > Copy from the app’s menu, or by using the Command-C keyboard shortcut. The system enables the Copy command for your app when it detects copyable content.

For example, the following code enables people to copy all of the strings that they select in a [List](../List.zh-Hans.md):

```swift
struct CopyableExample: View {
    let strings = ["Alpha", "Beta", "Gamma"]
    @State private var selection: Set<String> = []

    var body: some View {
        List(strings, id: \.self, selection: $selection) {
            Text($0)
        }
        .copyable(Array(selection))
    }
}
```

The command copies each item’s representation as specified by the item’s conformance to the [doc://com.apple.documentation/documentation/CoreTransferable/Transferable] protocol. The above example records selection using each list item’s corresponding string, and strings conform to the `Transferable` protocol by default. For more complex cases, you might need to take additional steps.

For example, the following code displays colors composed from a list of `Item` instances that contain both a color and its name, as well as an identifier. The list manages selection using item identifiers:

```swift
struct Item: Identifiable, Transferable {
    let color: Color
    let name: String
    let id = UUID()

    static var transferRepresentation: some TransferRepresentation {
        ProxyRepresentation(exporting: \.name)
    }
}

struct CopyableIDExample: View {
    let items: [Item] = [
        Item(color: .red, name: "red"),
        Item(color: .green, name: "green"),
        Item(color: .blue, name: "blue")
    ]

    @State private var selection: Set<Item.ID> = []

    var body: some View {
        List(items, selection: $selection) { item in
            item.color
        }
        .copyable(items.filter { selection.contains($0.id) })
    }
}
```

This example does two things that the previous example didn’t have to:

- It converts the list of selected item identifiers into a list of selected items for use with the copyable modifier.
- It ensures that the copyable items conform to the [doc://com.apple.documentation/documentation/CoreTransferable/Transferable] protocol, using the item’s `name` property as the representation.

When someone copies the first item in the list, which appears in the interface as a red rectangle, and then pastes into a text editor, they get the string “red”.



## Copying transferable items

- **cuttable(for:action:)**: Specifies an action that moves items to the Clipboard in response to the system’s Cut command.
- **pasteDestination(for:action:validator:)**: Specifies an action that adds validated items to a view in response to the system’s Paste command.

