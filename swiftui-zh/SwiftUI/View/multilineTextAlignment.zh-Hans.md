--- 来源：https://developer.apple.com/documentation/SwiftUI/View/multilineTextAlignment(_:)

抓取时间：2025-12-02T17:35:12Z

---

# multilineTextAlignment(_:)

**实例方法**

设置包含多行文本的文本视图的对齐方式。

## 声明

```swift
nonisolated func multilineTextAlignment(_ alignment: TextAlignment) -> some View

```

## 参数

- **alignment**：用于对齐视图中多行文本的值。

## 返回值

一个对齐其包含的多行文本实例的视图。

## 说明

使用此修饰符设置多行文本块的对齐方式。例如，该修饰符会将以下 [Text](../Text.zh-Hans.md) 视图的内容居中显示：

```swift
Text("This is a block of text that shows up in a text element as multiple lines.\("\n") Here we have chosen to center this text.")
    .frame(width: 200)
    .multilineTextAlignment(.center)
```

上述示例中的文本跨越多行，原因如下：

- 换行符会引入一个换行符。

- 框架修饰符限制了文本视图的可用空间，默认情况下，文本视图会将超出可用宽度的行自动换行。因此，显式换行符之前的文本会换行显示三行，之后的文本则使用两行。

无论换行的原因是什么，该修饰符都会将对齐方式应用于视图中的所有文本行：

该修饰符对仅包含一行文本的 [Text](../Text.zh-Hans.md) 视图无效，因为文本视图的宽度与其最宽行的宽度完全匹配。如果您想对齐整个文本视图而不是其内容，请设置其容器的对齐方式，例如 [VStack](../VStack.zh-Hans.md) 或使用 [frame(minWidth:idealWidth:maxWidth:minHeight:idealHeight:maxHeight:alignment:)](frame_minWidth_idealWidth_maxWidth_minHeight_idealHeight_maxHeight_alignment.zh-Hans.md) 修饰符创建的框架。

该修饰符还会影响其他文本容器类型的内容对齐方式，例如 [TextEditor](../TextEditor.zh-Hans.md) 和 [TextField](../TextField.zh-Hans.md)。在这些情况下，即使视图仅包含一行文本，该修饰符也会设置对齐方式，因为视图的宽度并非由其包含的文本宽度决定。

该修饰符通过设置环境中的 [multilineTextAlignment](../EnvironmentValues/multilineTextAlignment.zh-Hans.md) 值来工作，因此它会影响已修改视图层次结构中的所有文本容器。例如，您可以将该修饰符应用于 [VStack](../VStack.zh-Hans.md) 来配置堆栈中的所有文本视图。

## 多行文本格式设置

- **lineSpacing(_:)**：设置此视图中文本行之间的间距。

- **lineSpacing**：一行文本底部到下一行文本顶部的距离（以磅为单位）。

- **multilineTextAlignment**：一个环境值，指示文本视图在内容换行或包含换行符时如何对齐文本行。


---
source: https://developer.apple.com/documentation/SwiftUI/View/multilineTextAlignment(_:)
crawled: 2025-12-02T17:35:12Z
---

# multilineTextAlignment(_:)

**Instance Method**

Sets the alignment of a text view that contains multiple lines of text.

## Declaration

```swift
nonisolated func multilineTextAlignment(_ alignment: TextAlignment) -> some View

```

## Parameters

- **alignment**: A value that you use to align multiple lines of text within a view.

## Return Value

A view that aligns the lines of multiline [Text](../Text.zh-Hans.md) instances it contains.

## Discussion

Use this modifier to set an alignment for a multiline block of text. For example, the modifier centers the contents of the following [Text](../Text.zh-Hans.md) view:

```swift
Text("This is a block of text that shows up in a text element as multiple lines.\("\n") Here we have chosen to center this text.")
    .frame(width: 200)
    .multilineTextAlignment(.center)
```

The text in the above example spans more than one line because:

- The newline character introduces a line break.
- The frame modifier limits the space available to the text view, and by default a text view wraps lines that don’t fit in the available width. As a result, the text before the explicit line break wraps to three lines, and the text after uses two lines.

The modifier applies the alignment to the all the lines of text in the view, regardless of why wrapping occurs:



The modifier has no effect on a [Text](../Text.zh-Hans.md) view that contains only one line of text, because a text view has a width that exactly matches the width of its widest line. If you want to align an entire text view rather than its contents, set the aligment of its container, like a [VStack](../VStack.zh-Hans.md) or a frame that you create with the [frame(minWidth:idealWidth:maxWidth:minHeight:idealHeight:maxHeight:alignment:)](frame_minWidth_idealWidth_maxWidth_minHeight_idealHeight_maxHeight_alignment.zh-Hans.md) modifier.



The modifier also affects the content alignment of other text container types, like [TextEditor](../TextEditor.zh-Hans.md) and [TextField](../TextField.zh-Hans.md). In those cases, the modifier sets the alignment even when the view contains only a single line because view’s width isn’t dictated by the width of the text it contains.

The modifier operates by setting the [multilineTextAlignment](../EnvironmentValues/multilineTextAlignment.zh-Hans.md) value in the environment, so it affects all the text containers in the modified view hierarchy. For example, you can apply the modifier to a [VStack](../VStack.zh-Hans.md) to configure all the text views inside the stack.

## Formatting multiline text

- **lineSpacing(_:)**: Sets the amount of space between lines of text in this view.
- **lineSpacing**: The distance in points between the bottom of one line fragment and the top of the next.
- **multilineTextAlignment**: An environment value that indicates how a text view aligns its lines when the content wraps or contains newlines.

