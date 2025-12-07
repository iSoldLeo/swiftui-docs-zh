--- 来源：https://developer.apple.com/documentation/SwiftUI/Font/system(_:design:weight:)

抓取时间：2025-12-01T11:07:04Z

---

# system(_:design:weight:)

**类型方法**

获取使用指定样式、设计和字重的系统字体。

## 声明

```swift
static func system(_ style: Font.TextStyle, design: Font.Design? = nil, weight: Font.Weight? = nil) -> Font
```

## 说明

使用此方法创建具有指定属性的系统字体。以下示例创建了一个系统字体，其文本样式为 [body](TextStyle/body.zh-Hans.md)，设计为 [serif](../Font/Design/serif.zh-Hans.md)，字重为 [bold](../Font/Weight/bold.zh-Hans.md)，并使用视图修饰符 [font(_:)](../View/font.zh-Hans.md) 将该字体应用到视图 [Text](../Text.zh-Hans.md)：

```swift
Text("Hello").font(.system(.body, design: .serif, weight: .bold))
```

`design` 和 `weight` 参数均为可选参数。如果省略其中任何一个，系统将使用该参数的默认值。默认值通常分别为 [default](../Font/Design/default.zh-Hans.md) 和 [regular](../Font/Weight/regular.zh-Hans.md)，但可能因上下文而异。

## 获取系统字体

- **system(size:weight:design:)**：指定要使用的系统字体，以及样式、字重和要应用于文本的任何设计参数。

- **Font.Design**：用于字体的设计。

- **Font.TextStyle**：用于字体的动态文本样式。

- **Font.Weight**：用于字体的字重。


---
source: https://developer.apple.com/documentation/SwiftUI/Font/system(_:design:weight:)
crawled: 2025-12-01T11:07:04Z
---

# system(_:design:weight:)

**Type Method**

Gets a system font that uses the specified style, design, and weight.

## Declaration

```swift
static func system(_ style: Font.TextStyle, design: Font.Design? = nil, weight: Font.Weight? = nil) -> Font
```

## Discussion

Use this method to create a system font that has the specified properties. The following example creates a system font with the [body](TextStyle/body.zh-Hans.md) text style, a [serif](../Font/Design/serif.zh-Hans.md) design, and a [bold](../Font/Weight/bold.zh-Hans.md) weight, and applies the font to a [Text](../Text.zh-Hans.md) view using the [font(_:)](../View/font.zh-Hans.md) view modifier:

```swift
Text("Hello").font(.system(.body, design: .serif, weight: .bold))
```

The `design` and `weight` parameters are both optional. If you omit either, the system uses a default value for that parameter. The default values are typically [default](../Font/Design/default.zh-Hans.md) and [regular](../Font/Weight/regular.zh-Hans.md), respectively, but might vary depending on the context.

## Getting system fonts

- **system(size:weight:design:)**: Specifies a system font to use, along with the style, weight, and any design parameters you want applied to the text.
- **Font.Design**: A design to use for fonts.
- **Font.TextStyle**: A dynamic text style to use for fonts.
- **Font.Weight**: A weight to use for fonts.

