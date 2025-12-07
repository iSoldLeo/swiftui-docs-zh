---
来源： https://developer.apple.com/documentation/SwiftUI/EnvironmentValues/multilineTextAlignment
抓取时间： 2025-12-02T17:35:13Z
---

# 多行文本对齐方式

**实例属性**

表示文本视图在内容换行或包含换行符时如何对齐行列的环境值。

## 声明

```swift
var multilineTextAlignment: TextAlignment { get set }
```

## 讨论

通过应用[multilineTextAlignment(_:)](../View/multilineTextAlignment.zh-Hans.md)视图修饰符为视图层次结构设置此值。层次结构中显示文本的视图（如 [Text](../Text.zh-Hans.md) 或 [TextEditor](../TextEditor.zh-Hans.md) ）会从环境中读取该值，并相应地调整文本对齐方式。

该值对于只包含一行文本的[Text](../Text.zh-Hans.md) 视图没有影响，因为文本视图的宽度与其最宽行的宽度完全一致。如果要对齐整个文本视图而不是其内容，请设置其容器的对齐方式，如[VStack](../VStack.zh-Hans.md) 或使用[frame(minWidth:idealWidth:maxWidth:minHeight:idealHeight:maxHeight:alignment:)](../View/frame_minWidth_idealWidth_maxWidth_minHeight_idealHeight_maxHeight_alignment.zh-Hans.md) 修改器创建的框架。



##格式化多行文本

- **lineSpacing(_:)**：设置该视图中文本行间距的大小。
- **lineSpacing**：一个行片段的底部与下一个行片段的顶部之间的距离（以点为单位）。
- **multilineTextAlignment(_:)**：文本视图的对齐方式：设置包含多行文本的文本视图的对齐方式。


---
source: https://developer.apple.com/documentation/SwiftUI/EnvironmentValues/multilineTextAlignment
crawled: 2025-12-02T17:35:13Z
---

# multilineTextAlignment

**Instance Property**

An environment value that indicates how a text view aligns its lines when the content wraps or contains newlines.

## Declaration

```swift
var multilineTextAlignment: TextAlignment { get set }
```

## Discussion

Set this value for a view hierarchy by applying the [multilineTextAlignment(_:)](../View/multilineTextAlignment.zh-Hans.md) view modifier. Views in the hierarchy that display text, like [Text](../Text.zh-Hans.md) or [TextEditor](../TextEditor.zh-Hans.md), read the value from the environment and adjust their text alignment accordingly.

This value has no effect on a [Text](../Text.zh-Hans.md) view that contains only one line of text, because a text view has a width that exactly matches the width of its widest line. If you want to align an entire text view rather than its contents, set the aligment of its container, like a [VStack](../VStack.zh-Hans.md) or a frame that you create with the [frame(minWidth:idealWidth:maxWidth:minHeight:idealHeight:maxHeight:alignment:)](../View/frame_minWidth_idealWidth_maxWidth_minHeight_idealHeight_maxHeight_alignment.zh-Hans.md) modifier.



## Formatting multiline text

- **lineSpacing(_:)**: Sets the amount of space between lines of text in this view.
- **lineSpacing**: The distance in points between the bottom of one line fragment and the top of the next.
- **multilineTextAlignment(_:)**: Sets the alignment of a text view that contains multiple lines of text.

