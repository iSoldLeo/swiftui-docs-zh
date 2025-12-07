--- 来源：https://developer.apple.com/documentation/SwiftUI/Font/monospaced(_:)

抓取时间：2025-12-01T11:07:27Z

---

# monospaced(_:)

**实例方法**

返回一个字体，该字体在与基础字体相同的字体系列中添加或移除等宽设计。

## 声明

```swift
func monospaced(_ isActive: Bool) -> Font
```

## 返回值

如果基础字体系列中存在合适的字体，则返回添加或移除等宽设计的字体；否则返回默认字体。

## 说明

如果同一字体系列中没有合适的字体，SwiftUI 将返回默认字体。

以下示例将 `monospaced()` 修饰符添加到默认系统字体，然后将此字体应用于 [Text](../Text.zh-Hans.md) 视图：

```swift
struct ContentView: View {
    let myFont = Font
        .system(size: 24)
        .monospaced(true)

    var body: some View {
        Text("Hello, world!")
            .font(myFont)
            .padding()
            .navigationTitle("Monospaced")
    }
}
```

SwiftUI 可能会为标准用户界面字体（例如 [title](title.zh-Hans.md) 或使用 [system(_:design:)](system___design.zh-Hans.md) 创建的系统字体）提供不同的等宽字体替换，而对于使用 [custom(_:size:)](custom___size.zh-Hans.md) 按名称创建的相同字体，则提供的替换字体可能不同。

[font(_:)](../View/font.zh-Hans.md) 修饰符会将字体应用于视图中的所有文本。要在同一 `Text` 视图中将等宽文本与其他样式混合使用，请使用 [doc://com.apple.SwiftUI/documentation/SwiftUI/Text/init(_:)-1a4oh] 初始化器为文本视图的内容使用适当样式的 [doc://com.apple.documentation/documentation/Foundation/AttributedString] 字体。您可以使用 [doc://com.apple.documentation/documentation/Foundation/AttributedString/init(markdown:options:baseURL:)-52n3u] 初始化器提供一个 Markdown 格式的字符串，其中包含反引号语法 (`…`)，以便将代码语调应用于属性字符串的特定范围。


---
source: https://developer.apple.com/documentation/SwiftUI/Font/monospaced(_:)
crawled: 2025-12-01T11:07:27Z
---

# monospaced(_:)

**Instance Method**

Returns a font adding or removing fixed-width design from the same family as the base font.

## Declaration

```swift
func monospaced(_ isActive: Bool) -> Font
```

## Return Value

A font with the fixed-width design added or removed, from the same family as the base font, if one is available, and a default font otherwise.

## Discussion

If there’s no suitable font face in the same family, SwiftUI returns a default font.

The following example adds the `monospaced()` modifier to the default system font, then applies this font to a [Text](../Text.zh-Hans.md) view:

```swift
struct ContentView: View {
    let myFont = Font
        .system(size: 24)
        .monospaced(true)

    var body: some View {
        Text("Hello, world!")
            .font(myFont)
            .padding()
            .navigationTitle("Monospaced")
    }
}
```



SwiftUI may provide different fixed-width replacements for standard user interface fonts (such as [title](title.zh-Hans.md), or a system font created with [system(_:design:)](system___design.zh-Hans.md)) than for those same fonts when created by name with [custom(_:size:)](custom___size.zh-Hans.md).

The [font(_:)](../View/font.zh-Hans.md) modifier applies the font to all text within the view. To mix fixed-width text with other styles in the same `Text` view, use the [doc://com.apple.SwiftUI/documentation/SwiftUI/Text/init(_:)-1a4oh] initializer to use an appropriately-styled [doc://com.apple.documentation/documentation/Foundation/AttributedString] for the text view’s content. You can use the [doc://com.apple.documentation/documentation/Foundation/AttributedString/init(markdown:options:baseURL:)-52n3u] initializer to provide a Markdown-formatted string containing the backtick-syntax (`…`) to apply code voice to specific ranges of the attributed string.

