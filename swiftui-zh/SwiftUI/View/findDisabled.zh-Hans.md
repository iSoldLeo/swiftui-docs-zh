--- 来源：https://developer.apple.com/documentation/SwiftUI/View/findDisabled(_:)

抓取时间：2025-12-02T17:31:55Z

---

# findDisabled(_:)

**实例方法**

禁用文本编辑器中的查找和替换功能。

## 声明

```swift
nonisolated func findDisabled(_ isDisabled: Bool = true) -> some View

```

## 参数

- **isDisabled**：一个布尔值，指示是否禁用文本编辑器的查找和替换功能。

## 返回值

一个禁用查找和替换功能的视图。

## 讨论

添加此修饰符可确保用户无法激活 [TextEditor](../TextEditor.zh-Hans.md) 的查找和替换界面：

```swift
TextEditor(text: $text)
    .findDisabled()
```

禁用查找操作时，也会隐式禁用替换操作。如果只想禁用替换，请改用 [replaceDisabled(_:)](replaceDisabled.zh-Hans.md)。

使用此修饰符还可以阻止使用 [findNavigator(isPresented:)](findNavigator_isPresented.zh-Hans.md) 方法以编程方式呈现查找和替换界面。请确保将禁用修饰符放置在靠近文本编辑器的位置，以便生效：

```swift
TextEditor(text: $text)
    .findDisabled(isDisabled)
    .findNavigator(isPresented: $isPresented)
```

如果在视图层次结构的多个级别应用此修饰符，则最靠近文本编辑器的调用优先。例如，用户可以为以下示例中的第一个文本编辑器启用查找和替换功能，但不能为第二个文本编辑器启用：

```swift
VStack {
    TextEditor(text: $text1)
        .findDisabled(false)
    TextEditor(text: $text2)
}
.findDisabled(true)
```

## 在视图中搜索文本

- **findNavigator(isPresented:)**：以编程方式显示文本编辑器视图的查找和替换界面。

- **replaceDisabled(_:)**：阻止在文本编辑器中执行替换操作。

- **FindContext**：支持文本编辑的视图的查找导航器状态。


---
source: https://developer.apple.com/documentation/SwiftUI/View/findDisabled(_:)
crawled: 2025-12-02T17:31:55Z
---

# findDisabled(_:)

**Instance Method**

Prevents find and replace operations in a text editor.

## Declaration

```swift
nonisolated func findDisabled(_ isDisabled: Bool = true) -> some View

```

## Parameters

- **isDisabled**: A Boolean value that indicates whether to disable the find and replace interface for a text editor.

## Return Value

A view that disables the find and replace interface.

## Discussion

Add this modifier to ensure that people can’t activate the find and replace interface for a [TextEditor](../TextEditor.zh-Hans.md):

```swift
TextEditor(text: $text)
    .findDisabled()
```

When you disable the find operation, you also implicitly disable the replace operation. If you want to only disable replace, use [replaceDisabled(_:)](replaceDisabled.zh-Hans.md) instead.

Using this modifer also prevents programmatic find and replace interface presentation using the [findNavigator(isPresented:)](findNavigator_isPresented.zh-Hans.md) method. Be sure to place the disabling modifier closer to the text editor for this to work:

```swift
TextEditor(text: $text)
    .findDisabled(isDisabled)
    .findNavigator(isPresented: $isPresented)
```

If you apply this modifer at multiple levels of a view hierarchy, the call closest to the text editor takes precedence. For example, people can activate find and replace for the first text editor in the following example, but not the second:

```swift
VStack {
    TextEditor(text: $text1)
        .findDisabled(false)
    TextEditor(text: $text2)
}
.findDisabled(true)
```

## Searching for text in a view

- **findNavigator(isPresented:)**: Programmatically presents the find and replace interface for text editor views.
- **replaceDisabled(_:)**: Prevents replace operations in a text editor.
- **FindContext**: The status of the find navigator for views which support text editing.

