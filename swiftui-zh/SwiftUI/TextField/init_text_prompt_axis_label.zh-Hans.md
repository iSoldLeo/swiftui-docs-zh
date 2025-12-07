---
来源：https://developer.apple.com/documentation/SwiftUI/TextField/init(文本:提示:轴:标签:)
抓取时间：2025-12-02T17:51:44Z
---

# init(text:prompt:axis:label:)

**Initializer**

创建带有首选轴的文本字段，提示符由 `Text` 生成。

## 声明

```swift
nonisolated init(text: Binding<String>, prompt: Text? = nil, axis: Axis, @ViewBuilder label: () -> Label)
```

## 参数

- **text**：要显示和编辑的文本。
- **prompt**：代表文本字段提示的`Text`，可指导用户在文本字段中输入什么内容。
- **axis**：当文本无法容纳在可用空间时滚动文本的轴。
- **label**：描述文本字段用途的视图。

## 讨论

指定一个首选轴，当文本字段的内容不适合在可用空间内滚动时，应在该轴上滚动。根据字段的样式，该轴可能不受尊重。

使用[onSubmit(of:_:)](../View/onSubmit_of.zh-Hans.md) 修改器可在用户提交此文本字段时调用一个操作。

## 创建可滚动文本字段

- **init(_:text:axis:)**：创建一个文本字段，其首选轴和文本标签由本地化标题字符串生成。
- **init(_:text:prompt:axis:)**：创建具有首选轴的文本字段，文本标签由本地化标题字符串生成。


---
source: https://developer.apple.com/documentation/SwiftUI/TextField/init(text:prompt:axis:label:)
crawled: 2025-12-02T17:51:44Z
---

# init(text:prompt:axis:label:)

**Initializer**

Creates a text field with a preferred axis and a prompt generated from a `Text`.

## Declaration

```swift
nonisolated init(text: Binding<String>, prompt: Text? = nil, axis: Axis, @ViewBuilder label: () -> Label)
```

## Parameters

- **text**: The text to display and edit.
- **prompt**: A `Text` representing the prompt of the text field which provides users with guidance on what to type into the text field.
- **axis**: The axis in which to scroll text when it doesn’t fit in the available space.
- **label**: A view that describes the purpose of the text field.

## Discussion

Specify a preferred axis in which the text field should scroll its content when it does not fit in the available space. Depending on the style of the field, this axis may not be respected.

Use the [onSubmit(of:_:)](../View/onSubmit_of.zh-Hans.md) modifier to invoke an action whenever the user submits this text field.

## Creating a scrollable text field

- **init(_:text:axis:)**: Creates a text field with a preferred axis and a text label generated from a localized title string.
- **init(_:text:prompt:axis:)**: Creates a text field with a preferred axis and a text label generated from a localized title string.

