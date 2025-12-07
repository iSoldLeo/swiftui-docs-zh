--- 来源：https://developer.apple.com/documentation/SwiftUI/ContentTransition/numericText(value:)

抓取时间：2025-12-01T11:06:18Z

---

# numericText(value:)

**类型方法**

创建一个内容过渡效果，用于显示数字的视图（`Text`）。

## 声明

```swift
static func numericText(value: Double) -> ContentTransition
```

## 参数

- **value**：被动画化的视图（`Text`）所代表的值。文本更改时，新旧值之间的差异将用于确定动画方向。

## 返回值

一个新的内容过渡效果。

## 讨论

以下示例创建了一个显示特定值的文本视图，并将相同的值分配给关联的过渡效果：

```swift
Text("\(value)")
    .contentTransition(.numericText(value: value))
```

## 获取内容过渡效果

- **identity**：标识内容过渡效果，表示内容更改不应有动画。

- **interpolate**：一种内容过渡效果，表示视图在过渡期间会尝试在适当情况下对其内容进行插值。

- **numericText(countsDown:)**：创建一个内容过渡效果，旨在与显示数字文本的视图一起使用。`Text` 在某些环境中，文本更改将启用一个非标准过渡效果，该效果专为递增或递减的数字字符而设计。

- **opacity**：一种内容过渡效果，表示内容在插入时从透明淡入到不透明，在移除时从不透明淡入到透明。

- **symbolEffect**：一种内容过渡效果，它会将默认的符号效果过渡应用于插入或移除视图层级结构中的符号图像。其他视图不受此过渡效果的影响。

- **symbolEffect(_:options:)**：创建一个内容过渡效果，它会将符号替换动画应用于所应用的符号图像。


---
source: https://developer.apple.com/documentation/SwiftUI/ContentTransition/numericText(value:)
crawled: 2025-12-01T11:06:18Z
---

# numericText(value:)

**Type Method**

Creates a content transition intended to be used with `Text` views displaying numbers.

## Declaration

```swift
static func numericText(value: Double) -> ContentTransition
```

## Parameters

- **value**: The value represented by the `Text` view being animated. The difference between the old and new values when the text changes will be used to determine the animation direction.

## Return Value

A new content transition.

## Discussion

The example below creates a text view displaying a particular value, assigning the same value to the associated transition:

```swift
Text("\(value)")
    .contentTransition(.numericText(value: value))
```

## Getting content transitions

- **identity**: The identity content transition, which indicates that content changes shouldn’t animate.
- **interpolate**: A content transition that indicates the views attempt to interpolate their contents during transitions, where appropriate.
- **numericText(countsDown:)**: Creates a content transition intended to be used with `Text` views displaying numeric text. In certain environments changes to the text will enable a nonstandard transition tailored to numeric characters that count up or down.
- **opacity**: A content transition that indicates content fades from transparent to opaque on insertion, and from opaque to transparent on removal.
- **symbolEffect**: A content transition that applies the default symbol effect transition to symbol images within the inserted or removed view hierarchy. Other views are unaffected by this transition.
- **symbolEffect(_:options:)**: Creates a content transition that applies the symbol Replace animation to symbol images that it is applied to.

