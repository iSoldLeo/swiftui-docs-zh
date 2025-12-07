--- 来源：https://developer.apple.com/documentation/SwiftUI/ContentTransition/symbolEffect
抓取时间：2025-12-03T06:17:09Z

---

# symbolEffect

**类型属性**

一种内容过渡效果，它将默认的符号效果过渡应用于插入或移除视图层级结构中的符号图像。其他视图不受此过渡效果的影响。

## 声明

```swift
static var symbolEffect: ContentTransition { get }
```

## 获取内容过渡效果

- **identity**：标识内容过渡效果，表示内容更改不应有动画。

- **interpolate**：一种内容过渡效果，表示视图在过渡期间会尝试插值其内容（如果适用）。

- **numericText(countsDown:)**：创建一个内容过渡效果，用于显示数字文本的 `Text` 视图。在某些环境下，更改文本将启用一个非标准过渡效果，该效果专为递增或递减的数字字符而设计。

- **numericText(value:)**：创建一个内容过渡效果，用于显示数字的 `Text` 视图。

- **opacity**：一个内容过渡效果，指示内容在插入时从透明淡入到不透明，在移除时从不透明淡入到透明。

- **symbolEffect(_:options:)**：创建一个内容过渡效果，将符号替换动画应用于其所应用的符号图像。


---
source: https://developer.apple.com/documentation/SwiftUI/ContentTransition/symbolEffect
crawled: 2025-12-03T06:17:09Z
---

# symbolEffect

**Type Property**

A content transition that applies the default symbol effect transition to symbol images within the inserted or removed view hierarchy. Other views are unaffected by this transition.

## Declaration

```swift
static var symbolEffect: ContentTransition { get }
```

## Getting content transitions

- **identity**: The identity content transition, which indicates that content changes shouldn’t animate.
- **interpolate**: A content transition that indicates the views attempt to interpolate their contents during transitions, where appropriate.
- **numericText(countsDown:)**: Creates a content transition intended to be used with `Text` views displaying numeric text. In certain environments changes to the text will enable a nonstandard transition tailored to numeric characters that count up or down.
- **numericText(value:)**: Creates a content transition intended to be used with `Text` views displaying numbers.
- **opacity**: A content transition that indicates content fades from transparent to opaque on insertion, and from opaque to transparent on removal.
- **symbolEffect(_:options:)**: Creates a content transition that applies the symbol Replace animation to symbol images that it is applied to.

