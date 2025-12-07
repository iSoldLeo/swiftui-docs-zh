--- 来源：https://developer.apple.com/documentation/SwiftUI/ContentTransition/numericText(countsDown:)

抓取时间：2025-12-01T11:06:17Z

---

# numericText(countsDown:)

**类型方法**

创建一个内容过渡效果，用于显示数字文本的视图。在某些环境下，更改文本将启用一个非标准过渡效果，该效果专为向上或向下计数的数字字符而设计。

## 声明



## 参数

- 如果文本表示的数字向下计数，则返回 True。

## 返回值

一个新的内容过渡效果。

## 获取内容过渡效果

- **identity**：标识内容过渡效果，表示内容更改不应有动画。

- **interpolate**：内容过渡效果，表示视图在过渡期间会尝试插值其内容（如适用）。

- **numericText(value:)**：创建用于显示数字的视图（`Text`）的内容过渡效果。

- **opacity**：内容过渡效果，表示插入时内容从透明淡入到不透明，移除时内容从不透明淡入到透明。

- **symbolEffect**：内容过渡效果，将默认符号效果过渡应用于插入或移除视图层级结构中的符号图像。其他视图不受此过渡效果的影响。

- **symbolEffect(_:options:)**：创建一个内容过渡效果，将符号替换动画应用于指定的符号图像。


---
source: https://developer.apple.com/documentation/SwiftUI/ContentTransition/numericText(countsDown:)
crawled: 2025-12-01T11:06:17Z
---

# numericText(countsDown:)

**Type Method**

Creates a content transition intended to be used with `Text` views displaying numeric text. In certain environments changes to the text will enable a nonstandard transition tailored to numeric characters that count up or down.

## Declaration

```swift
static func numericText(countsDown: Bool = false) -> ContentTransition
```

## Parameters

- **countsDown**: True if the numbers represented by the text are counting downwards.

## Return Value

A new content transition.

## Getting content transitions

- **identity**: The identity content transition, which indicates that content changes shouldn’t animate.
- **interpolate**: A content transition that indicates the views attempt to interpolate their contents during transitions, where appropriate.
- **numericText(value:)**: Creates a content transition intended to be used with `Text` views displaying numbers.
- **opacity**: A content transition that indicates content fades from transparent to opaque on insertion, and from opaque to transparent on removal.
- **symbolEffect**: A content transition that applies the default symbol effect transition to symbol images within the inserted or removed view hierarchy. Other views are unaffected by this transition.
- **symbolEffect(_:options:)**: Creates a content transition that applies the symbol Replace animation to symbol images that it is applied to.

