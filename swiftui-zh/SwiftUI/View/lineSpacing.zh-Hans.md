--- 来源：https://developer.apple.com/documentation/SwiftUI/View/lineSpacing(_:)

抓取时间：2025-11-30T21:20:18Z

---

# lineSpacing(_:)

**实例方法**

设置此视图中文本行之间的间距。

## 声明

```swift
nonisolated func lineSpacing(_ lineSpacing: CGFloat) -> some View

```

## 参数

- **lineSpacing**：一行底部到下一行顶部之间的间距，单位为磅。

## 说明

使用 `lineSpacing(_:)` 设置视图中文本元素的行间距。

在以下示例中的 [Text](../Text.zh-Hans.md) 视图中，当文本字段在该视图内换行时，每行底部与下一行顶部之间的距离为 10 磅。将 `lineSpacing(_:)` 应用于视图层次结构，会将行间距应用于视图中包含的所有文本元素。

```swift
Text("This is a string in a TextField with 10 point spacing applied between the bottom of one line and the top of the next.")
    .frame(width: 200, height: 200, alignment: .leading)
    .lineSpacing(10)
```

## 格式化多行文本

- **lineSpacing**：一行文本底部与下一行文本顶部之间的距离（以磅为单位）。

- **multilineTextAlignment(_:)**：设置包含多行文本的文本视图的对齐方式。

- **multilineTextAlignment**：一个环境值，指示当内容换行或包含换行符时，文本视图如何对齐其行。


---
source: https://developer.apple.com/documentation/SwiftUI/View/lineSpacing(_:)
crawled: 2025-11-30T21:20:18Z
---

# lineSpacing(_:)

**Instance Method**

Sets the amount of space between lines of text in this view.

## Declaration

```swift
nonisolated func lineSpacing(_ lineSpacing: CGFloat) -> some View

```

## Parameters

- **lineSpacing**: The amount of space between the bottom of one line and the top of the next line in points.

## Discussion

Use `lineSpacing(_:)` to set the amount of spacing from the bottom of one line to the top of the next for text elements in the view.

In the [Text](../Text.zh-Hans.md) view in the example below, 10 points separate the bottom of one line to the top of the next as the text field wraps inside this view. Applying `lineSpacing(_:)` to a view hierarchy applies the line spacing to all text elements contained in the view.

```swift
Text("This is a string in a TextField with 10 point spacing applied between the bottom of one line and the top of the next.")
    .frame(width: 200, height: 200, alignment: .leading)
    .lineSpacing(10)
```



## Formatting multiline text

- **lineSpacing**: The distance in points between the bottom of one line fragment and the top of the next.
- **multilineTextAlignment(_:)**: Sets the alignment of a text view that contains multiple lines of text.
- **multilineTextAlignment**: An environment value that indicates how a text view aligns its lines when the content wraps or contains newlines.

