--- 来源：https://developer.apple.com/documentation/SwiftUI/ContentTransition/interpolate
抓取时间：2025-12-03T06:17:07Z

---

# interpolate

**类型属性**

内容过渡效果，指示视图在过渡期间尝试对其内容进行插值（如适用）。

## 声明

```swift
static let interpolate: ContentTransition
```

## 讨论

当文本视图具有相同的字符串时，文本视图可以进行过渡插值。匹配的字形对可以对其颜色、位置、大小和任何可变属性的变化进行动画处理。插值可以应用于同一案例内，但不能应用于案例之间，也不能应用于完全不同的字体之间。[Design](../Font/Design.zh-Hans.md)例如，您可以对字体变体 [thin](../Font/Weight/thin.zh-Hans.md) 和 [black](../Font/Weight/black.zh-Hans.md) 之间的变化进行插值，因为它们都属于 [Weight](../Font/Weight.zh-Hans.md)。但是，您无法对字体的默认样式及其斜体版本进行插值，因为它们是不同的字体。任何无法显示插值动画的变化都会改用不透明度动画。

使用 [init(systemName:)](../Image/init_systemName.zh-Hans.md) 初始化器创建的符号图像的工作方式与文本相同：同一符号内的更改会尝试对符号的路径进行插值。当插值不可用时，系统会改用不透明度过渡。

## 获取内容过渡

- **identity**：标识内容过渡，表示内容更改不应使用动画。

- **numericText(countsDown:)**：创建一个内容过渡效果，用于显示数字文本的视图（`Text`）。在某些环境下，更改文本将启用一个非标准过渡效果，该效果专为递增或递减的数字字符而设计。

- **numericText(value:)**：创建一个内容过渡效果，用于显示数字的视图（`Text`）。

- **opacity**：一个内容过渡效果，指示内容在插入时从透明淡入到不透明，在移除时从不透明淡入到透明。

- **symbolEffect**：一个内容过渡效果，将默认的符号效果过渡应用于插入或移除视图层级结构中的符号图像。其他视图不受此过渡效果的影响。

- **symbolEffect(_:options:)**：创建一个内容过渡效果，将符号替换动画应用于其所应用的符号图像。


---
source: https://developer.apple.com/documentation/SwiftUI/ContentTransition/interpolate
crawled: 2025-12-03T06:17:07Z
---

# interpolate

**Type Property**

A content transition that indicates the views attempt to interpolate their contents during transitions, where appropriate.

## Declaration

```swift
static let interpolate: ContentTransition
```

## Discussion

Text views can interpolate transitions when the text views have identical strings. Matching glyph pairs can animate changes to their color, position, size, and any variable properties. Interpolation can apply within a [Design](../Font/Design.zh-Hans.md) case, but not between cases, or between entirely different fonts. For example, you can interpolate a change between [thin](../Font/Weight/thin.zh-Hans.md) and [black](../Font/Weight/black.zh-Hans.md) variations of a font, since these are both cases of [Weight](../Font/Weight.zh-Hans.md). However, you can’t interpolate between the default design of a font and its Italic version, because these are different fonts. Any changes that can’t show an interpolated animation use an opacity animation instead.

Symbol images created with the [init(systemName:)](../Image/init_systemName.zh-Hans.md) initializer work the same way as text: changes within the same symbol attempt to interpolate the symbol’s paths. When interpolation is unavailable, the system uses an opacity transition instead.

## Getting content transitions

- **identity**: The identity content transition, which indicates that content changes shouldn’t animate.
- **numericText(countsDown:)**: Creates a content transition intended to be used with `Text` views displaying numeric text. In certain environments changes to the text will enable a nonstandard transition tailored to numeric characters that count up or down.
- **numericText(value:)**: Creates a content transition intended to be used with `Text` views displaying numbers.
- **opacity**: A content transition that indicates content fades from transparent to opaque on insertion, and from opaque to transparent on removal.
- **symbolEffect**: A content transition that applies the default symbol effect transition to symbol images within the inserted or removed view hierarchy. Other views are unaffected by this transition.
- **symbolEffect(_:options:)**: Creates a content transition that applies the symbol Replace animation to symbol images that it is applied to.

