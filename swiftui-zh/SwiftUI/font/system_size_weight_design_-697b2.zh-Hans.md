--- 来源：https://developer.apple.com/documentation/SwiftUI/Font/system(size:weight:design:)-697b2

抓取时间：2025-12-01T11:07:05Z

---

# system(size:weight:design:)

**类型方法**

指定要使用的系统字体，以及样式、字重和要应用于文本的任何设计参数。

## 声明

```swift
static func system(size: CGFloat, weight: Font.Weight? = nil, design: Font.Design? = nil) -> Font
```

## 说明

使用此函数通过同时指定大小、字重和字体设计来创建系统字体。以下样式将系统字体设置为 17 磅，文本为 [semibold](../Font/Weight/semibold.zh-Hans.md)：

```swift
Text("Hello").font(.system(size: 17, weight: .semibold))
```

以下样式将文本设置为 17 磅，文本为 [bold](../Font/Weight/bold.zh-Hans.md)，并对系统字体应用 `serif` [Design](../Font/Design.zh-Hans.md)：

```swift
Text("Hello").font(.system(size: 17, weight: .bold, design: .serif))
```

`weight` 和 `design` 均为可选。如果您未提供 `weight` 或 `design`，系统可以根据当前上下文选择一个字体，但在某些情况下，该字体可能不是 [regular](../Font/Weight/regular.zh-Hans.md) 或 [default](../Font/Design/default.zh-Hans.md)。以下示例使用 [rounded](../Font/Design/rounded.zh-Hans.md) 设计将文本样式设置为 17 磅系统字体，其字重可根据当前上下文而定：

```swift
Text("Hello").font(.system(size: 17, design: .rounded))
```

## 获取系统字体

- **system(_:design:weight:)**：获取使用指定样式、设计和字重的系统字体。

- **Font.Design**：用于字体的设计。

- **Font.TextStyle**：用于字体的动态文本样式。

- **Font.Weight**：用于字体的字重。


---
source: https://developer.apple.com/documentation/SwiftUI/Font/system(size:weight:design:)-697b2
crawled: 2025-12-01T11:07:05Z
---

# system(size:weight:design:)

**Type Method**

Specifies a system font to use, along with the style, weight, and any design parameters you want applied to the text.

## Declaration

```swift
static func system(size: CGFloat, weight: Font.Weight? = nil, design: Font.Design? = nil) -> Font
```

## Discussion

Use this function to create a system font by specifying the size and weight, and a type design together. The following styles the system font as 17 point, [semibold](../Font/Weight/semibold.zh-Hans.md) text:

```swift
Text("Hello").font(.system(size: 17, weight: .semibold))
```

While the following styles the text as 17 point [bold](../Font/Weight/bold.zh-Hans.md), and applies a `serif` [Design](../Font/Design.zh-Hans.md) to the system font:

```swift
Text("Hello").font(.system(size: 17, weight: .bold, design: .serif))
```

Both `weight` and `design` can be optional. When you do not provide a `weight` or `design`, the system can pick one based on the current context, which may not be [regular](../Font/Weight/regular.zh-Hans.md) or [default](../Font/Design/default.zh-Hans.md) in certain context. The following example styles the text as 17 point system font using [rounded](../Font/Design/rounded.zh-Hans.md) design, while its weight can depend on the current context:

```swift
Text("Hello").font(.system(size: 17, design: .rounded))
```

## Getting system fonts

- **system(_:design:weight:)**: Gets a system font that uses the specified style, design, and weight.
- **Font.Design**: A design to use for fonts.
- **Font.TextStyle**: A dynamic text style to use for fonts.
- **Font.Weight**: A weight to use for fonts.

