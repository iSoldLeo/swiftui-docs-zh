--- 来源：https://developer.apple.com/documentation/SwiftUI/Font/system(size:weight:design:)-73a88

抓取时间：2025-12-03T06:18:14Z

---

# system(size:weight:design:)

**类型方法**

指定要使用的系统字体，以及样式、字重和要应用于文本的任何设计参数。

## 声明

```swift
static func system(size: CGFloat, weight: Font.Weight = .regular, design: Font.Design = .default) -> Font
```

## 说明

使用此函数通过同时指定大小、字重和字体设计来创建系统字体。以下代码将系统字体样式设置为 17 磅，文本为 [semibold](../Font/Weight/semibold.zh-Hans.md)：

```swift
Text("Hello").font(.system(size: 17, weight: .semibold))
```

以下代码将文本样式设置为 17 磅 [bold](../Font/Weight/bold.zh-Hans.md)，并对系统字体应用 `serif` [Design](../Font/Design.zh-Hans.md)：

```swift
Text("Hello").font(.system(size: 17, weight: .bold, design: .serif))
```

如果您想使用默认字体 [Weight](../Font/Weight.zh-Hans.md) ([regular](../Font/Weight/regular.zh-Hans.md))，则无需在方法中指定 `weight`。以下示例将文本样式设置为 17 磅 [regular](../Font/Weight/regular.zh-Hans.md)，并使用 [rounded](../Font/Design/rounded.zh-Hans.md) 系统字体：

```swift
Text("Hello").font(.system(size: 17, design: .rounded))
```

## 已弃用符号

- **system(_:design:)**：获取具有给定文本样式和设计的系统字体。


---
source: https://developer.apple.com/documentation/SwiftUI/Font/system(size:weight:design:)-73a88
crawled: 2025-12-03T06:18:14Z
---

# system(size:weight:design:)

**Type Method**

Specifies a system font to use, along with the style, weight, and any design parameters you want applied to the text.

## Declaration

```swift
static func system(size: CGFloat, weight: Font.Weight = .regular, design: Font.Design = .default) -> Font
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

If you want to use the default [Weight](../Font/Weight.zh-Hans.md) ([regular](../Font/Weight/regular.zh-Hans.md)), you don’t need to specify the `weight` in the method. The following example styles the text as 17 point [regular](../Font/Weight/regular.zh-Hans.md), and uses a [rounded](../Font/Design/rounded.zh-Hans.md) system font:

```swift
Text("Hello").font(.system(size: 17, design: .rounded))
```

## Deprecated symbols

- **system(_:design:)**: Gets a system font with the given text style and design.

