--- 来源：https://developer.apple.com/documentation/swiftui/text

抓取时间：2025-12-04T13:40:04Z

---

# 文本视图

**Structure**

用于显示一行或多行只读文本的视图。

## 声明

```swift
@frozen struct Text
```

## 概述

文本视图使用适合当前平台的字体在应用的用户界面中绘制字符串。[body](font/body.zh-Hans.md) 您可以使用视图修饰符 [font(_:)](View/font.zh-Hans.md) 选择其他标准字体，例如 [title](font/title.zh-Hans.md) 或 [caption](font/caption.zh-Hans.md)。

```swift
Text("Hamlet")
    .font(.title)
```

如果您需要更精细地控制文本样式，可以使用相同的修饰符来配置系统字体或选择自定义字体。您还可以应用视图修饰符，例如 [bold()](Text/bold.zh-Hans.md) 或 [italic()](Text/italic.zh-Hans.md)，以进一步调整格式。

```swift
Text("by William Shakespeare")
    .font(.system(size: 12, weight: .light, design: .serif))
    .italic()
```

要对文本的特定部分应用样式，您可以从 [doc://com.apple.documentation/documentation/Foundation/AttributedString] 创建文本视图，这样您就可以使用 Markdown 来设置文本的样式。您可以混合使用字符串属性和 SwiftUI 修饰符，字符串属性的优先级更高。

```swift
let attributedString = try! AttributedString(
    markdown: "_Hamlet_ by William Shakespeare")

var body: some View {
    Text(attributedString)
        .font(.system(size: 12, weight: .light, design: .serif))
}
```

文本视图始终使用显示其渲染内容所需的空间，但您可以影响视图的布局。例如，您可以使用 [frame(width:height:alignment:)](View/frame_width_height_alignment.zh-Hans.md) 修饰符向视图指定尺寸。如果视图接受该建议，但文本无法完全适应可用空间，则视图会结合换行、收紧、缩放和截断等方式使其适应空间。例如，如果文本视图的宽度为 `100` 点，但高度没有限制，则长字符串可能会换行：

```swift
Text("To be, or not to be, that is the question:")
    .frame(width: 100)
```

使用 [lineLimit(_:)](View/lineLimit.zh-Hans.md)、[allowsTightening(_:)](View/allowsTightening.zh-Hans.md)、[minimumScaleFactor(_:)](View/minimumScaleFactor.zh-Hans.md) 和 [truncationMode(_:)](View/truncationMode.zh-Hans.md) 等修饰符来配置视图如何处理空间限制。例如，如果将固定宽度与 `1` 的行数限制结合使用，则超出该空间的文本将被截断：

```swift
Text("Brevity is the soul of wit.")
    .frame(width: 100)
    .lineLimit(1)
```

### 字符串本地化

如果您使用字符串字面量初始化文本视图，则该视图将使用 [init(_:tableName:bundle:comment:)](Text/init___tableName_bundle_comment.zh-Hans.md) 初始化器，该初始化器会将字符串解释为本地化键，并在您指定的表中查找该键；如果您未指定表，则在默认表中查找。

```swift
Text("pencil") // Searches the default table in the main bundle.
```

对于同时本地化为英语和西班牙语的应用，上述视图将分别向英语用户和西班牙语用户显示“pencil”和“lápiz”。如果视图无法执行本地化，则会显示键值。例如，如果同一应用缺少丹麦语本地化，则视图将向丹麦语用户显示“pencil”。同样，如果应用缺少任何本地化信息，则无论使用何种语言环境，都会显示“pencil”（铅笔）。

要显式地绕过字符串字面量的本地化，请使用 [init(verbatim:)](Text/init_verbatim.zh-Hans.md) 初始化器。

```swift
Text(verbatim: "pencil") // Displays the string "pencil" in any locale.
```

如果使用变量值初始化文本视图，则该视图会使用 [doc://com.apple.SwiftUI/documentation/SwiftUI/Text/init(_:)-9d1g4] 初始化器，该初始化器不会对字符串进行本地化。但是，您可以先创建一个 [LocalizedStringKey](LocalizedStringKey.zh-Hans.md) 实例来请求本地化，这将触发 [init(_:tableName:bundle:comment:)](Text/init___tableName_bundle_comment.zh-Hans.md) 初始化器：

```swift
// Don't localize a string variable...
Text(writingImplement)

// ...unless you explicitly convert it to a localized string key.
Text(LocalizedStringKey(writingImplement))
```

本地化字符串变量时，您可以像处理字符串字面量一样，省略可选的初始化参数来使用默认表（如上面的示例所示）。

当需要组合多个文本片段来编写复杂的字符串时，请使用字符串插值：

```swift
let name: String = //…
Text("Hello, \(name)")
```

此操作会在本地化字符串文件中查找 `"Hello, %@"` 本地化键，并在将文本渲染到屏幕之前，将格式说明符 `%@` 替换为 `name` 的值。

使用字符串插值可以确保应用程序中的文本在所有语言环境中都能正确本地化，尤其是在从右到左的语言中。

如果您只想对插值文本的部分内容进行样式设置，同时确保内容仍能正确本地化，请插值 `Text` 或 [doc://com.apple.documentation/documentation/Foundation/AttributedString]：

```swift
let name = Text(person.name).bold()
Text("Hello, \(name)")
```

上面的示例使用 [doc://com.apple.SwiftUI/documentation/SwiftUI/LocalizedStringKey/StringInterpolation/appendInterpolation(_:)-4qyfo]，它会在本地化字符串文件中查找 `"Hello, %@"`，并插值粗体文本，以呈现 `name` 的值。

使用 [doc://com.apple.SwiftUI/documentation/SwiftUI/LocalizedStringKey/StringInterpolation/appendInterpolation(_:)-5m52e]，您可以在文本中插值 [Image](Image.zh-Hans.md)。

## 创建文本视图

- **init(_:tableName:bundle:comment:)**：创建一个文本视图，用于显示由键标识的本地化内容。

- **init(_:)**：创建一个文本视图，用于显示带样式的属性内容。

- **init(verbatim:)**：创建一个文本视图，显示未本地化的字符串字面量。

- **init(_:style:)**：创建一个实例，使用特定样式显示本地化的日期和时间。

- **init(_:format:)**：创建一个文本视图，显示由相应格式样式支持的非字符串类型的格式化表示。

- **init(_:formatter:)**：创建一个文本视图，显示 Foundation 对象的格式化表示。

- **init(timerInterval:pauseTime:countsDown:showsHours:)**：创建一个实例，显示在指定时间间隔内计数的计时器。

## 选择字体

- **font(_:)**：设置视图中文本的默认字体。

- **fontWeight(_:)**：设置文本的字体粗细。

- **fontDesign(_:)**：设置文本的字体样式。

- **fontWidth(_:)**：设置文本的字体宽度。

## 设置视图文本样式

- **foregroundStyle(_:)**：设置此视图显示的文本样式。

- **bold()**：对文本字体应用粗体或强调效果。

- **bold(_:)**：对文本应用粗体。

- **italic()**：对文本应用斜体。

- **italic(_:)**：对文本应用斜体。

- **strikethrough(_:color:)**：对文本应用删除线。

- **strikethrough(_:pattern:color:)**：为文本添加删除线。

- **underline(_:color:)**：为文本添加下划线。

- **underline(_:pattern:color:)**：为文本添加下划线。

- **monospaced(_:)**：尽可能将文本字体修改为当前字体的等宽版本。

- **monospacedDigit()**：将文本视图的字体修改为使用等宽数字，同时保持其他字符按比例间距。

- **kerning(_:)**：设置字符间距（或字距调整）。

- **tracking(_:)**：设置文本的字距。

- **baselineOffset(_:)**：设置文本相对于基线的垂直偏移量。

- **Text.Case**：用于转换文本中字符大小写的方案。

- **Text.DateStyle**：用于显示 `Date` 的预定义样式。

- **Text.LineStyle**：用于绘制 `StrikethroughStyleAttribute` 和 `UnderlineStyleAttribute` 线条的样式描述。

## 将文本适应可用空间

- **textScale(_:isEnabled:)**：对文本应用文本缩放比例。

- **Text.Scale**：定义文本缩放比例。

- **Text.TruncationMode**：当文本行过长而无法适应可用空间时，要应用的截断类型。

## 文本本地化

- **typesettingLanguage(_:isEnabled:)**：指定排版语言。

## 配置旁白

- **speechAdjustedPitch(_:)**：提高或降低朗读文本的音调。

- **speechAlwaysIncludesPunctuation(_:)**：设置旁白是否始终朗读文本视图中的所有标点符号。

- **speechAnnouncementsQueued(_:)**：控制是否将待处理的语音提示排队到现有语音之后，而不是打断正在进行的语音。

- **speechSpellsOutCharacters(_:)**：设置旁白是否逐字符朗读文本视图的内容。

## 提供辅助功能信息

- **accessibilityHeading(_:)**：设置此标题的辅助功能级别。

- **accessibilityLabel(_:)**：向视图添加描述其内容的标签。

- **accessibilityTextContentType(_:)**：设置辅助功能文本内容类型。

## 合并文本视图

- **+(_:_:)**：将两个文本视图中的文本合并到一个新的文本视图中。

## 已弃用符号

- **foregroundColor(_:)**：设置此视图显示的文本颜色。

## 结构体

- **Text.AlignmentStrategy**：如果未显式提供值，SwiftUI 推断文本对齐方式的方法。

- **Text.Layout**：描述视图树的布局和自定义属性的值。

- **Text.LayoutKey**：提供查询子树中所有文本视图的属性值的首选项键。

- **Text.WritingDirectionStrategy**：SwiftUI 在未显式提供值时推断正确书写方向的方式。

## 实例方法

- **customAttribute(_:)**：向文本视图添加自定义属性。

- **textVariant(_:)**：控制文本大小变体的选择方式。

## 显示文本

- **Label**：用户界面项的标准标签，由图标和标题组成。

- **labelStyle(_:)**：设置此视图中标签的样式。

## 符合以下规范

- Copyable

- Equatable

- Sendable

- SendableMetatype

- View


---
source: https://developer.apple.com/documentation/swiftui/text
crawled: 2025-12-04T13:40:04Z
---

# Text

**Structure**

A view that displays one or more lines of read-only text.

## Declaration

```swift
@frozen struct Text
```

## Overview

A text view draws a string in your app’s user interface using a [body](font/body.zh-Hans.md) font that’s appropriate for the current platform. You can choose a different standard font, like [title](font/title.zh-Hans.md) or [caption](font/caption.zh-Hans.md), using the [font(_:)](View/font.zh-Hans.md) view modifier.

```swift
Text("Hamlet")
    .font(.title)
```



If you need finer control over the styling of the text, you can use the same modifier to configure a system font or choose a custom font. You can also apply view modifiers like [bold()](Text/bold.zh-Hans.md) or [italic()](Text/italic.zh-Hans.md) to further adjust the formatting.

```swift
Text("by William Shakespeare")
    .font(.system(size: 12, weight: .light, design: .serif))
    .italic()
```



To apply styling within specific portions of the text, you can create the text view from an [doc://com.apple.documentation/documentation/Foundation/AttributedString], which in turn allows you to use Markdown to style runs of text. You can mix string attributes and SwiftUI modifiers, with the string attributes taking priority.

```swift
let attributedString = try! AttributedString(
    markdown: "_Hamlet_ by William Shakespeare")

var body: some View {
    Text(attributedString)
        .font(.system(size: 12, weight: .light, design: .serif))
}
```



A text view always uses exactly the amount of space it needs to display its rendered contents, but you can affect the view’s layout. For example, you can use the [frame(width:height:alignment:)](View/frame_width_height_alignment.zh-Hans.md) modifier to propose specific dimensions to the view. If the view accepts the proposal but the text doesn’t fit into the available space, the view uses a combination of wrapping, tightening, scaling, and truncation to make it fit. With a width of `100` points but no constraint on the height, a text view might wrap a long string:

```swift
Text("To be, or not to be, that is the question:")
    .frame(width: 100)
```



Use modifiers like [lineLimit(_:)](View/lineLimit.zh-Hans.md), [allowsTightening(_:)](View/allowsTightening.zh-Hans.md), [minimumScaleFactor(_:)](View/minimumScaleFactor.zh-Hans.md), and [truncationMode(_:)](View/truncationMode.zh-Hans.md) to configure how the view handles space constraints. For example, combining a fixed width and a line limit of `1` results in truncation for text that doesn’t fit in that space:

```swift
Text("Brevity is the soul of wit.")
    .frame(width: 100)
    .lineLimit(1)
```



### Localizing strings

If you initialize a text view with a string literal, the view uses the [init(_:tableName:bundle:comment:)](Text/init___tableName_bundle_comment.zh-Hans.md) initializer, which interprets the string as a localization key and searches for the key in the table you specify, or in the default table if you don’t specify one.

```swift
Text("pencil") // Searches the default table in the main bundle.
```

For an app localized in both English and Spanish, the above view displays “pencil” and “lápiz” for English and Spanish users, respectively. If the view can’t perform localization, it displays the key instead. For example, if the same app lacks Danish localization, the view displays “pencil” for users in that locale. Similarly, an app that lacks any localization information displays “pencil” in any locale.

To explicitly bypass localization for a string literal, use the [init(verbatim:)](Text/init_verbatim.zh-Hans.md) initializer.

```swift
Text(verbatim: "pencil") // Displays the string "pencil" in any locale.
```

If you initialize a text view with a variable value, the view uses the [doc://com.apple.SwiftUI/documentation/SwiftUI/Text/init(_:)-9d1g4] initializer, which doesn’t localize the string. However, you can request localization by creating a [LocalizedStringKey](LocalizedStringKey.zh-Hans.md) instance first, which triggers the [init(_:tableName:bundle:comment:)](Text/init___tableName_bundle_comment.zh-Hans.md) initializer instead:

```swift
// Don't localize a string variable...
Text(writingImplement)

// ...unless you explicitly convert it to a localized string key.
Text(LocalizedStringKey(writingImplement))
```

When localizing a string variable, you can use the default table by omitting the optional initialization parameters — as in the above example — just like you might for a string literal.

When composing a complex string, where there is a need to assemble multiple pieces of text, use string interpolation:

```swift
let name: String = //…
Text("Hello, \(name)")
```

This would look up the `"Hello, %@"` localization key in the localized string file and replace the format specifier `%@` with the value of `name` before rendering the text on screen.

Using string interpolation ensures that the text in your app can be localized correctly in all locales, especially in right-to-left languages.

If you desire to style only parts of interpolated text while ensuring that the content can still be localized correctly, interpolate `Text` or [doc://com.apple.documentation/documentation/Foundation/AttributedString]:

```swift
let name = Text(person.name).bold()
Text("Hello, \(name)")
```

The example above uses [doc://com.apple.SwiftUI/documentation/SwiftUI/LocalizedStringKey/StringInterpolation/appendInterpolation(_:)-4qyfo] and will look up the `"Hello, %@"` in the localized string file and interpolate a bold text rendering the value of  `name`.

Using [doc://com.apple.SwiftUI/documentation/SwiftUI/LocalizedStringKey/StringInterpolation/appendInterpolation(_:)-5m52e] you can interpolate [Image](Image.zh-Hans.md) in text.

## Creating a text view

- **init(_:tableName:bundle:comment:)**: Creates a text view that displays localized content identified by a key.
- **init(_:)**: Creates a text view that displays styled attributed content.
- **init(verbatim:)**: Creates a text view that displays a string literal without localization.
- **init(_:style:)**: Creates an instance that displays localized dates and times using a specific style.
- **init(_:format:)**: Creates a text view that displays the formatted representation of a nonstring type supported by a corresponding format style.
- **init(_:formatter:)**: Creates a text view that displays the formatted representation of a Foundation object.
- **init(timerInterval:pauseTime:countsDown:showsHours:)**: Creates an instance that displays a timer counting within the provided interval.

## Choosing a font

- **font(_:)**: Sets the default font for text in the view.
- **fontWeight(_:)**: Sets the font weight of the text.
- **fontDesign(_:)**: Sets the font design of the text.
- **fontWidth(_:)**: Sets the font width of the text.

## Styling the view’s text

- **foregroundStyle(_:)**: Sets the style of the text displayed by this view.
- **bold()**: Applies a bold or emphasized treatment to the fonts of the text.
- **bold(_:)**: Applies a bold font weight to the text.
- **italic()**: Applies italics to the text.
- **italic(_:)**: Applies italics to the text.
- **strikethrough(_:color:)**: Applies a strikethrough to the text.
- **strikethrough(_:pattern:color:)**: Applies a strikethrough to the text.
- **underline(_:color:)**: Applies an underline to the text.
- **underline(_:pattern:color:)**: Applies an underline to the text.
- **monospaced(_:)**: Modifies the font of the text to use the fixed-width variant of the current font, if possible.
- **monospacedDigit()**: Modifies the text view’s font to use fixed-width digits, while leaving other characters proportionally spaced.
- **kerning(_:)**: Sets the spacing, or kerning, between characters.
- **tracking(_:)**: Sets the tracking for the text.
- **baselineOffset(_:)**: Sets the vertical offset for the text relative to its baseline.
- **Text.Case**: A scheme for transforming the capitalization of characters within text.
- **Text.DateStyle**: A predefined style used to display a `Date`.
- **Text.LineStyle**: Description of the style used to draw the line for `StrikethroughStyleAttribute` and `UnderlineStyleAttribute`.

## Fitting text into available space

- **textScale(_:isEnabled:)**: Applies a text scale to the text.
- **Text.Scale**: Defines text scales
- **Text.TruncationMode**: The type of truncation to apply to a line of text when it’s too long to fit in the available space.

## Localizing text

- **typesettingLanguage(_:isEnabled:)**: Specifies the language for typesetting.

## Configuring voiceover

- **speechAdjustedPitch(_:)**: Raises or lowers the pitch of spoken text.
- **speechAlwaysIncludesPunctuation(_:)**: Sets whether VoiceOver should always speak all punctuation in the text view.
- **speechAnnouncementsQueued(_:)**: Controls whether to queue pending announcements behind existing speech rather than interrupting speech in progress.
- **speechSpellsOutCharacters(_:)**: Sets whether VoiceOver should speak the contents of the text view character by character.

## Providing accessibility information

- **accessibilityHeading(_:)**: Sets the accessibility level of this heading.
- **accessibilityLabel(_:)**: Adds a label to the view that describes its contents.
- **accessibilityTextContentType(_:)**: Sets an accessibility text content type.

## Combining text views

- **+(_:_:)**: Concatenates the text in two text views in a new text view.

## Deprecated symbols

- **foregroundColor(_:)**: Sets the color of the text displayed by this view.

## Structures

- **Text.AlignmentStrategy**: The way SwiftUI infers the appropriate text alignment if no value is explicitly provided.
- **Text.Layout**: A value describing the layout and custom attributes of a tree of `Text` views.
- **Text.LayoutKey**: A preference key that provides the `Text.Layout` values for all text views in the queried subtree.
- **Text.WritingDirectionStrategy**: The way SwiftUI infers the appropriate writing direction if no value is explicitly provided.

## Instance Methods

- **customAttribute(_:)**: Adds a custom attribute to the text view.
- **textVariant(_:)**: Controls the way text size variants are chosen.

## Displaying text

- **Label**: A standard label for user interface items, consisting of an icon with a title.
- **labelStyle(_:)**: Sets the style for labels within this view.

## Conforms To

- Copyable
- Equatable
- Sendable
- SendableMetatype
- View

