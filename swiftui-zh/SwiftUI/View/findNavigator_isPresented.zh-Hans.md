--- 来源：https://developer.apple.com/documentation/SwiftUI/View/findNavigator(isPresented:)

抓取时间：2025-11-30T21:16:58Z

---

# findNavigator(isPresented:)

**实例方法**

以编程方式呈现文本编辑器视图的查找和替换界面。

## 声明

```swift
nonisolated func findNavigator(isPresented: Binding<Bool>) -> some View

```

## 参数

- **isPresented**：绑定到一个布尔值，用于控制查找和替换界面的呈现。

## 返回值

当 `isPresented` 为 `true` 时，显示查找和替换界面的视图。

## 讨论

将此修饰符添加到 [TextEditor](../TextEditor.zh-Hans.md) 或包含至少一个文本编辑器的视图层级结构中，即可控制查找和替换界面的显示。将 `isPresented` 绑定设置为 `true` 时，系统会显示该界面；将其设置为 `false` 时，系统会隐藏该界面。以下示例根据工具栏按钮的状态显示和隐藏该界面：

```swift
TextEditor(text: $text)
    .findNavigator(isPresented: $isPresented)
    .toolbar {
        Toggle(isOn: $isPresented) {
            Label("Find", systemImage: "magnifyingglass")
        }
    }
```

查找和替换界面允许用户在文本编辑器中搜索指定字符串的实例，并可选择将搜索字符串的实例替换为另一个字符串。用户还可以使用内置控件（例如菜单和键盘快捷键）来显示和隐藏该界面。SwiftUI 会更新 `isPresented` 以反映用户的操作。

如果文本编辑器视图当前未处于焦点状态，即使将 `isPresented` 设置为 `true`，系统仍然会显示查找和替换界面。如果视图层级结构包含多个编辑器，则显示查找和替换界面的编辑器是不确定的。

您可以通过将 [findDisabled(_:)](findDisabled.zh-Hans.md) 修饰符应用于文本编辑器来禁用其查找和替换界面。如果这样做，则将此修饰符的 `isPresented` 绑定设置为 `true` 将无效，但前提是禁用修饰符出现在更靠近文本编辑器的位置，例如：

```swift
TextEditor(text: $text)
    .findDisabled(isDisabled)
    .findNavigator(isPresented: $isPresented)
```

## 在视图中搜索文本

- **findDisabled(_:)**：阻止在文本编辑器中执行查找和替换操作。

- **replaceDisabled(_:)**：阻止在文本编辑器中进行替换操作。

- **FindContext**：支持文本编辑的视图的查找导航器状态。


---
source: https://developer.apple.com/documentation/SwiftUI/View/findNavigator(isPresented:)
crawled: 2025-11-30T21:16:58Z
---

# findNavigator(isPresented:)

**Instance Method**

Programmatically presents the find and replace interface for text editor views.

## Declaration

```swift
nonisolated func findNavigator(isPresented: Binding<Bool>) -> some View

```

## Parameters

- **isPresented**: A binding to a Boolean value that controls the presentation of the find and replace interface.

## Return Value

A view that presents the find and replace interface when `isPresented` is `true`.

## Discussion

Add this modifier to a [TextEditor](../TextEditor.zh-Hans.md), or to a view hierarchy that contains at least one text editor, to control the presentation of the find and replace interface. When you set the `isPresented` binding to `true`, the system shows the interface, and when you set it to `false`, the system hides the interface. The following example shows and hides the interface based on the state of a toolbar button:

```swift
TextEditor(text: $text)
    .findNavigator(isPresented: $isPresented)
    .toolbar {
        Toggle(isOn: $isPresented) {
            Label("Find", systemImage: "magnifyingglass")
        }
    }
```

The find and replace interface allows people to search for instances of a specified string in the text editor, and optionally to replace instances of the search string with another string. They can also show and hide the interface using built-in controls, like menus and keyboard shortcuts. SwiftUI updates `isPresented` to reflect the users’s actions.

If the text editor view isn’t currently in focus, the system still presents the find and replace interface when you set `isPresented` to `true`. If the view hierarchy contains multiple editors, the one that shows the find and replace interface is nondeterministic.

You can disable the find and replace interface for a text editor by applying the [findDisabled(_:)](findDisabled.zh-Hans.md) modifier to the editor. If you do that, setting this modifier’s `isPresented` binding to `true` has no effect, but only if the disabling modifier appears closer to the text editor, like this:

```swift
TextEditor(text: $text)
    .findDisabled(isDisabled)
    .findNavigator(isPresented: $isPresented)
```

## Searching for text in a view

- **findDisabled(_:)**: Prevents find and replace operations in a text editor.
- **replaceDisabled(_:)**: Prevents replace operations in a text editor.
- **FindContext**: The status of the find navigator for views which support text editing.

