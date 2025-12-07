--- 来源：https://developer.apple.com/documentation/SwiftUI/View/replaceDisabled(_:)

抓取时间：2025-11-30T21:17:00Z

---

# replaceDisabled(_:)

**实例方法**

禁用文本编辑器中的替换操作。

## 声明

```swift
nonisolated func replaceDisabled(_ isDisabled: Bool = true) -> some View

```

## 参数

- **isDisabled**：一个布尔值，指示是否禁用查找和替换界面中的文本替换功能。

## 返回值

一个禁用查找和替换界面替换功能的视图。

## 讨论

添加此修饰符可确保用户无法激活查找和替换界面的替换功能（[TextEditor](../TextEditor.zh-Hans.md)）：

```swift
TextEditor(text: $text)
    .replaceDisabled()
```

如果要同时禁用查找和替换功能，请改用 [findDisabled(_:)](findDisabled.zh-Hans.md) 修饰符。

使用此修饰符还会禁用您使用 [findNavigator(isPresented:)](findNavigator_isPresented.zh-Hans.md) 方法以编程方式呈现的查找和替换界面的替换功能。请确保将禁用修饰符放置在靠近文本编辑器的位置，以便生效：

```swift
TextEditor(text: $text)
    .replaceDisabled(isDisabled)
    .findNavigator(isPresented: $isPresented)
```

如果在视图层次结构的多个级别应用此修饰符，则最靠近文本编辑器的调用优先。例如，用户可以为以下示例中的第一个文本编辑器启用查找和替换功能，但只能为第二个文本编辑器启用查找功能：

```swift
VStack {
    TextEditor(text: $text1)
        .replaceDisabled(false)
    TextEditor(text: $text2)
}
.replaceDisabled(true)
```

## 在视图中搜索文本

- **findNavigator(isPresented:)**：以编程方式呈现文本编辑器视图的查找和替换界面。

- **findDisabled(_:)**：阻止在文本编辑器中执行查找和替换操作。

- **FindContext**：支持文本编辑的视图的查找导航器状态。


---
source: https://developer.apple.com/documentation/SwiftUI/View/replaceDisabled(_:)
crawled: 2025-11-30T21:17:00Z
---

# replaceDisabled(_:)

**Instance Method**

Prevents replace operations in a text editor.

## Declaration

```swift
nonisolated func replaceDisabled(_ isDisabled: Bool = true) -> some View

```

## Parameters

- **isDisabled**: A Boolean value that indicates whether text replacement in the find and replace interface is disabled.

## Return Value

A view that disables the replace feature of a find and replace interface.

## Discussion

Add this modifier to ensure that people can’t activate the replace feature of a find and replace interface for a [TextEditor](../TextEditor.zh-Hans.md):

```swift
TextEditor(text: $text)
    .replaceDisabled()
```

If you want to disable both find and replace, use the [findDisabled(_:)](findDisabled.zh-Hans.md) modifier instead.

Using this modifer also disables the replace feature of a find and replace interface that you present programmatically using the [findNavigator(isPresented:)](findNavigator_isPresented.zh-Hans.md) method. Be sure to place the disabling modifier closer to the text editor for this to work:

```swift
TextEditor(text: $text)
    .replaceDisabled(isDisabled)
    .findNavigator(isPresented: $isPresented)
```

If you apply this modifer at multiple levels of a view hierarchy, the call closest to the text editor takes precedence. For example, people can activate find and replace for the first text editor in the following example, but only find for the second:

```swift
VStack {
    TextEditor(text: $text1)
        .replaceDisabled(false)
    TextEditor(text: $text2)
}
.replaceDisabled(true)
```

## Searching for text in a view

- **findNavigator(isPresented:)**: Programmatically presents the find and replace interface for text editor views.
- **findDisabled(_:)**: Prevents find and replace operations in a text editor.
- **FindContext**: The status of the find navigator for views which support text editing.

