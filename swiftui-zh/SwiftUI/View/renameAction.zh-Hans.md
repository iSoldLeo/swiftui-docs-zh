--- 来源：https://developer.apple.com/documentation/SwiftUI/View/renameAction(_:)

抓取时间：2025-11-30T21:14:31Z

---

# renameAction(_:)

**实例方法**

设置重命名操作要运行的闭包。

## 声明

```swift
nonisolated func renameAction(_ action: @escaping () -> Void) -> some View

```

## 参数

- **action**：重命名时要运行的闭包。

## 返回值

具有指定重命名操作的视图。

## 说明

将此修饰符与 [RenameButton](../RenameButton.zh-Hans.md) 结合使用，以实现标准的重命名交互。重命名按钮从环境中获取其操作。使用此修饰符可以自定义提供给重命名按钮的操作。

```swift
struct RowView: View {
    @State private var text = ""
    @FocusState private var isFocused: Bool

    var body: some View {
        TextField(text: $item.name) {
            Text("Prompt")
        }
        .focused($isFocused)
        .contextMenu {
            RenameButton()
            // ... your own custom actions
        }
        .renameAction { isFocused = true }
}
```

当用户点击上下文菜单中的重命名按钮时，重命名操作会将 `isFocused` 属性设置为 true，从而使文本字段获得焦点。

## 重命名文档

- **RenameButton**：触发标准重命名操作的按钮。

- **rename**：激活标准重命名交互的操作。

- **RenameAction**：激活标准重命名交互的操作。


---
source: https://developer.apple.com/documentation/SwiftUI/View/renameAction(_:)
crawled: 2025-11-30T21:14:31Z
---

# renameAction(_:)

**Instance Method**

Sets a closure to run for the rename action.

## Declaration

```swift
nonisolated func renameAction(_ action: @escaping () -> Void) -> some View

```

## Parameters

- **action**: A closure to run when renaming.

## Return Value

A view that has the specified rename action.

## Discussion

Use this modifier in conjunction with the [RenameButton](../RenameButton.zh-Hans.md) to implement standard rename interactions. A rename button receives its action from the environment. Use this modifier to customize the action provided to the rename button.

```swift
struct RowView: View {
    @State private var text = ""
    @FocusState private var isFocused: Bool

    var body: some View {
        TextField(text: $item.name) {
            Text("Prompt")
        }
        .focused($isFocused)
        .contextMenu {
            RenameButton()
            // ... your own custom actions
        }
        .renameAction { isFocused = true }
}
```

When the user taps the rename button in the context menu, the rename action focuses the text field by setting the `isFocused` property to true.

## Renaming a document

- **RenameButton**: A button that triggers a standard rename action.
- **rename**: An action that activates the standard rename interaction.
- **RenameAction**: An action that activates a standard rename interaction.

