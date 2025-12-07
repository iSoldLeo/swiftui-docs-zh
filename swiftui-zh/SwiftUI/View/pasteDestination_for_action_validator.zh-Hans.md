--- 来源：https://developer.apple.com/documentation/SwiftUI/View/pasteDestination(for:action:validator:)

抓取时间：2025-11-30T21:27:40Z

---

# pasteDestination(for:action:validator:)

**实例方法**

指定一个操作，该操作响应系统的粘贴命令，将已验证的项目添加到视图中。

## 声明

```swift
nonisolated func pasteDestination<T>(for payloadType: T.Type = T.self, action: @escaping ([T]) -> Void, validator: @escaping ([T]) -> [T] = { $0 }) -> some View where T : Transferable

```

## 参数

- **payloadType**：粘贴目标接受的数据类型。该类型必须符合 [doc://com.apple.documentation/documentation/CoreTransferable/Transferable] 协议。

- **action**：当用户使用系统的粘贴命令粘贴一个或多个有效负载类型的项目时要执行的操作。闭包接受一个参数，即要粘贴的项目数组。 - **validator**：一个用于验证粘贴数据的闭包。SwiftUI 会在调用 `action` 闭包之前调用此闭包，并传入一个待验证的元素数组。检查这些元素，并返回一个仅包含输入数组中有效元素的数组。此闭包返回的数组将成为 `action` 闭包的输入。如果返回空数组，SwiftUI 将不会调用 `action` 闭包。

## 返回值

一个用户可以使用系统粘贴命令粘贴内容的视图。

## 说明

当用户发出粘贴命令时，可以使用此修饰符将剪贴板中的一个或多个元素粘贴到视图中。用户可以通过从应用程序菜单中选择“编辑”>“粘贴”，或使用快捷键 Command-V 来发出粘贴命令。当当前视图提供粘贴目标时，系统会为您的应用启用“粘贴”命令。

例如，以下代码允许用户将鸟类名称粘贴到列表中：

```swift
struct PasteDestinationExample: View {
    @State private var birds: [String] = []
    @State private var selection: Set<String> = []

    let knownBirds = ["owl", "parrot", "swift",
                      "sparrow", "robin", "bluebird"]

    var body: some View {
        List(birds, id: \.self, selection: $selection) {
            Text($0)
        }
        .pasteDestination(for: String.self) { values in
            birds.append(contentsOf: values)
        } validator: { values in
            values.filter { knownBirds.contains($0) }
        }
    }
}
```

粘贴目标仅处理类型与您指定的 `payloadType` 匹配的粘贴内容。上述示例中的列表仅接受字符串。

使用 `validator` 闭包将粘贴内容限制为在视图上下文中有意义的项。上述示例仅允许用户粘贴与已知鸟类名称列表中的某个名称匹配的字符串，因为该列表旨在仅包含鸟类。如果您不需要执行任何验证，则可以省略最后一个闭包。

## 复制可转移项

- **copyable(_:)**：指定要响应系统“复制”命令而复制的项列表。

- **cuttable(for:action:)**：指定响应系统“剪切”命令而将项目移动到剪贴板的操作。


---
source: https://developer.apple.com/documentation/SwiftUI/View/pasteDestination(for:action:validator:)
crawled: 2025-11-30T21:27:40Z
---

# pasteDestination(for:action:validator:)

**Instance Method**

Specifies an action that adds validated items to a view in response to the system’s Paste command.

## Declaration

```swift
nonisolated func pasteDestination<T>(for payloadType: T.Type = T.self, action: @escaping ([T]) -> Void, validator: @escaping ([T]) -> [T] = { $0 }) -> some View where T : Transferable

```

## Parameters

- **payloadType**: The type of data that the paste destination accepts. The type must conform to the [doc://com.apple.documentation/documentation/CoreTransferable/Transferable] protocol.
- **action**: The action to perform when someone uses the system’s Paste command to paste one or more items of the payload type. The closure takes one parameter, which is the array of items to paste.
- **validator**: A closure that you implement to validate the data to paste. SwiftUI calls this before it calls the `action` closure, and passes in an array of items to validate. Inspect the items, and return an array that includes only those from the input array that you consider valid. The array that you return from this closure becomes the input to the `action` closure. If you return an empty array, SwiftUI doesn’t call the `action` closure.

## Return Value

A view that people can paste into using the system Paste command.

## Discussion

Use this modifier to paste one or more items into a view from the Clipboard when someone issues a Paste command. People issue a Paste command by choosing Edit > Paste from the app’s menu, or by using the Command-V keyboard shortcut. The system enables the Paste command for your app when the view in focus provides a paste destination.

For example, the following code enables people to paste bird names into a list:

```swift
struct PasteDestinationExample: View {
    @State private var birds: [String] = []
    @State private var selection: Set<String> = []

    let knownBirds = ["owl", "parrot", "swift",
                      "sparrow", "robin", "bluebird"]

    var body: some View {
        List(birds, id: \.self, selection: $selection) {
            Text($0)
        }
        .pasteDestination(for: String.self) { values in
            birds.append(contentsOf: values)
        } validator: { values in
            values.filter { knownBirds.contains($0) }
        }
    }
}
```

The paste destination handles only pasted content with a type that matches the `payloadType` that you specify. The list in the above example only accepts strings.

Use the `validator` closure to restrict the pasted content to items that make sense in the context of the view. The above example allows people to paste only strings that match one of a known list of bird names because the list is meant to contain only birds. You can omit the final closure if you don’t need to perform any validation.



## Copying transferable items

- **copyable(_:)**: Specifies a list of items to copy in response to the system’s Copy command.
- **cuttable(for:action:)**: Specifies an action that moves items to the Clipboard in response to the system’s Cut command.

