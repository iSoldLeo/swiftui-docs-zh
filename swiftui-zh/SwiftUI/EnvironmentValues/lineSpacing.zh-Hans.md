---
来源： https://developer.apple.com/documentation/SwiftUI/EnvironmentValues/lineSpacing
抓取时间： 2025-12-02T17:35:11Z
---

# 行距

**实例属性**

一个线条片段的底部与下一个线条片段的顶部之间的距离（以点为单位）。

## 声明

```swift
var lineSpacing: CGFloat { get set }
```

## 讨论

这个值总是非负的。

## 多行文本格式

- **lineSpacing(_:)**：设置该视图中文本行间距的大小。
- **multilineTextAlignment(_:)**：设置包含多行文本的文本视图的对齐方式。
- **multilineTextAlignment**：环境值，用于指示文本视图在内容换行或包含换行符时的对齐方式。


---
source: https://developer.apple.com/documentation/SwiftUI/EnvironmentValues/lineSpacing
crawled: 2025-12-02T17:35:11Z
---

# lineSpacing

**Instance Property**

The distance in points between the bottom of one line fragment and the top of the next.

## Declaration

```swift
var lineSpacing: CGFloat { get set }
```

## Discussion

This value is always nonnegative.

## Formatting multiline text

- **lineSpacing(_:)**: Sets the amount of space between lines of text in this view.
- **multilineTextAlignment(_:)**: Sets the alignment of a text view that contains multiple lines of text.
- **multilineTextAlignment**: An environment value that indicates how a text view aligns its lines when the content wraps or contains newlines.

