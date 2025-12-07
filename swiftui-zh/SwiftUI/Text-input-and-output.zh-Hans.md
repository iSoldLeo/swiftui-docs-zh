--- 来源：https://developer.apple.com/documentation/SwiftUI/Text-input-and-output
抓取时间：2025-12-02T16:02:49Z

---

# 文本输入和输出

**API 集合**

显示格式化文本并获取用户输入的文本。

## 概述

要显示只读文本或只读文本与图像的组合，请分别使用内置的 [Text](Text.zh-Hans.md) 或 [Label](Label.zh-Hans.md) 视图。当需要收集用户输入的文本时，请使用相应的文本输入视图，例如 [TextField](TextField.zh-Hans.md) 或 [TextEditor](TextEditor.zh-Hans.md)。

您可以添加视图修饰符来控制文本的字体、可选中性、对齐方式、布局方向等。这些修饰符也会影响其他显示文本的视图，例如控件上的标签，即使您没有明确定义 [Text](Text.zh-Hans.md) 视图。

有关设计指南，请参阅《人机界面指南》中的 [doc://com.apple.documentation/design/Human-Interface-Guidelines/typography]。

## 显示文本

- **Text**：显示一行或多行只读文本的视图。

- **Label**：用户界面项的标准标签，由一个图标和一个标题组成。

- **labelStyle(_:)**：设置此视图中标签的样式。

## 获取文本输入

- **构建丰富的 SwiftUI 文本体验**：使用 SwiftUI 文本编辑器视图和属性字符串构建格式化文本编辑器。

- **TextField**：显示可编辑文本界面的控件。

- **textFieldStyle(_:)**：设置此视图中文本字段的样式。

- **SecureField**：用于安全地输入私密文本的控件。

- **TextEditor**：可以显示和编辑长文本的视图。

## 选择文本

- **textSelection(_:)**：控制用户是否可以在此视图中选择文本。

- **TextSelectability**：描述文本选择功能的类型。

- **TextSelection**：表示选定的文本。

- **textSelectionAffinity(_:)**：设置选择或光标相对于文本字符的方向。

- **textSelectionAffinity**：表示选择或光标相对于文本字符的方向或关联。当处理双向文本（包含从左到右 (LTR) 和从右到左 (RTL) 两种书写方式的文本，例如英语和阿拉伯语的组合）时，此概念尤为重要。

- **TextSelectionAffinity**：表示选区或光标相对于文本字符的方向或关联。当处理双向文本（包含从左到右 (LTR) 和从右到左 (RTL) 两种书写方式的文本，例如英语和阿拉伯语的组合）时，此概念尤为重要。

- **AttributedTextSelection**：表示已添加属性的文本选区。

## 设置字体

- **将自定义字体应用于文本**：在应用中添加并使用可随动态类型缩放的字体。

- **font(_:)**：设置此视图中文本的默认字体。

- **fontDesign(_:)**：设置此视图中文本的字体样式。

- **fontWeight(_:)**：设置此视图中文本的字体粗细。

- **fontWidth(_:)**：设置此视图中文本的字体宽度。

- **font**：此环境的默认字体。

- **Font**：环境相关的字体。

## 调整文本大小

- **textScale(_:isEnabled:)**：对视图中的文本应用文本缩放。

- **dynamicTypeSize(_:)**：将视图中的动态字体大小设置为给定值。

- **dynamicTypeSize**：当前的动态字体大小。

- **DynamicTypeSize**：动态字体大小，用于指定可缩放内容的大小。

- **ScaledMetric**：用于缩放数值的动态属性。

- **TextVariantPreference**：用于控制文本视图大小变体的协议。

- **FixedTextVariant**：默认文本变体首选项，选择最大可用变体。

- **SizeDependentTextVariant**：大小相关的变体首选项，允许文本在选择要显示的变体时考虑可用空间。

## 控制文本样式

- **bold(_:)**：为此视图中的文本应用粗体。

- **italic(_:)**：为此视图中的文本应用斜体。

- **underline(_:pattern:color:)**：为此视图中的文本应用下划线。

- **strikethrough(_:pattern:color:)**：为该视图中的文本添加删除线。

- **textCase(_:)**：设置该视图中文本显示时的大小写转换。

- **textCase**：使用环境语言设置，在显示时更改 `Text` 的大小写。

- **monospaced(_:)**：尽可能将所有子视图的字体修改为使用当前字体的等宽变体。

- **monospacedDigit()**：尽可能将所有子视图的字体修改为使用等宽数字，同时保持其他字符按比例间距。

- **AttributedTextFormattingDefinition**：用于定义视图中文本样式的协议。

- **AttributedTextValueConstraint**：用于定义特定属性值约束的协议。

- **AttributedTextFormatting**：与属性文本格式定义相关的类型的命名空间。

## 管理文本布局

- **truncationMode(_:)**：设置文本行过长而无法容纳在可用空间中的截断模式。

- **truncationMode**：指示布局如何截断最后一行文本以适应可用空间的值。

- **allowsTightening(_:)**：设置此视图中的文本是否可以在必要时压缩字符间距以使其适应一行。

- **allowsTightening**：指示是否应收紧字符间距以使文本适应可用空间的布尔值。

- **minimumScaleFactor(_:)**：设置此视图中文本缩小以适应可用空间的最小比例。

- **minimumScaleFactor**：字体大小缩小以适应可用空间的最小允许比例。

- **baselineOffset(_:)**：设置此视图中文本相对于其基线的垂直偏移量。

- **kerning(_:)**：设置此视图中文本的字符间距（或字距调整）。

- **tracking(_:)**：设置此视图中文本的字距。

- **flipsForRightToLeftLayoutDirection(_:)**：设置当布局方向为从右到左时，此视图是否水平镜像其内容。

- **TextAlignment**：文本沿水平轴的对齐位置。

## 文本渲染

- **使用 SwiftUI 创建视觉效果**：使用着色器和文本渲染器添加滚动效果、丰富的色彩处理、自定义过渡效果和高级效果。

- **TextAttribute**：可附加到文本视图的值，文本渲染器可以查询该值。

- **textRenderer(_:)**：返回一个新视图，其中的所有文本视图都将使用 `renderer` 进行绘制。

- **TextRenderer**：可替换默认文本视图渲染行为的值。

- **TextProxy**：自定义文本渲染器使用的文本视图代理。

## 限制多行文本的行数

- **lineLimit(_:)**：设置此视图中文本可占用的行数范围。

- **lineLimit(_:reservesSpace:)**：设置此视图中文本可占据的行数限制。

- **lineLimit**：视图中文本可占据的最大行数。

## 格式化多行文本

- **lineSpacing(_:)**：设置此视图中文本行之间的间距。

- **lineSpacing**：一行文本底部到下一行文本顶部的距离（以磅为单位）。

- **multilineTextAlignment(_:)**：设置包含多行文本的文本视图的对齐方式。

- **multilineTextAlignment**：一个环境值，指示当内容换行或包含换行符时，文本视图如何对齐其行。

## 日期和时间格式化

- **SystemFormatStyle**：用于实现 Apple 各平台通用设计的格式样式命名空间。

- **TimeDataSource**：时间相关数据源。

## 管理文本输入

- **autocorrectionDisabled(_:)**：设置是否禁用此视图的自动更正功能。

- **autocorrectionDisabled**：一个布尔值，用于确定视图层级结构是否启用自动更正功能。

- **keyboardType(_:)**：设置此视图的键盘类型。

- **scrollDismissesKeyboard(_:)**：配置可滚动内容与软件键盘的交互方式。

- **textContentType(_:)**：设置此视图的文本内容类型，系统会使用此类型在 macOS 用户输入文本时提供建议。

- **textInputAutocapitalization(_:)**：设置键盘中 Shift 键自动启用的频率。

- **TextInputAutocapitalization**：文本输入时应用的自动大写行为类型。

- **textInputCompletion(_:)**：将一个完整的字符串与此视图的值关联起来，以便用作文本输入建议。

- **textInputSuggestions(_:)**：配置此视图的文本输入建议。

- **textInputSuggestions(_:content:)**：配置此视图的文本输入建议。

- **textInputSuggestions(_:id:content:)**：配置此视图的文本输入建议。

- **textContentType(_:)**：设置此视图的文本内容类型，系统会使用此类型在用户于 watchOS 设备上输入文本时提供建议。

- **textContentType(_:)**：设置此视图的文本内容类型，系统会使用此类型在用户于 macOS 上输入文本时提供建议。

- **textContentType(_:)**：设置此视图的文本内容类型，系统会使用此类型在用户于 iOS 或 tvOS 设备上输入文本时提供建议。

- **TextInputFormattingControlPlacement**：定义每个平台上可用的系统文本格式控件的结构。

## 听写文本

- **searchDictationBehavior(_:)**：配置由可搜索修饰符配置的任何搜索字段的听写行为。

- **TextInputDictationActivation**

- **TextInputDictationBehavior**

## 配置写作工具行为

- **writingToolsBehavior(_:)**：指定环境中文本和文本输入的写作工具行为。

- **WritingToolsBehavior**：文本编辑工具的文本编辑体验和文本输入。

## 指定文本等效项

- **typeSelectEquivalent(_:)**：在集合（例如列表或表格）中设置显式类型选择等效文本。

## 文本本地化

- **准备视图本地化**：指定提示并添加字符串以本地化您的 SwiftUI 视图。

- **LocalizedStringKey**：用于在字符串文件或字符串字典文件中查找条目的键。

- **locale**：视图应使用的当前区域设置。

- **typesettingLanguage(_:isEnabled:)**：指定排版语言。

- **TypesettingLanguage**：定义如何确定文本的排版语言。

## 已弃用类型

- **ContentSizeCategory**：您可以为内容指定的大小。

## 视图

- **视图基础**：使用视图层级结构定义应用程序的视觉元素。

- **视图配置**：调整层级结构中视图的特性。

- **视图样式**：将内置和自定义的外观和行为应用于不同类型的视图。

- **Animations**：响应状态更改而创建平滑的视觉更新。

- **Images**：向应用程序的用户界面添加图像和符号。

- **控件和指示器**：显示值并获取用户选择。

- **菜单和命令**：提供对命令和控件的高效、上下文相关的访问方式。

- **Shapes**：使用颜色、渐变或其他图案描绘和填充内置和自定义形状。

- **绘图和图形**：利用图形效果和自定义绘图增强您的视图。


---
source: https://developer.apple.com/documentation/SwiftUI/Text-input-and-output
crawled: 2025-12-02T16:02:49Z
---

# Text input and output

**API Collection**

Display formatted text and get text input from the user.

## Overview

To display read-only text, or read-only text paired with an image, use the built-in [Text](Text.zh-Hans.md) or [Label](Label.zh-Hans.md) views, respectively. When you need to collect text input from the user, use an appropriate text input view, like [TextField](TextField.zh-Hans.md) or [TextEditor](TextEditor.zh-Hans.md).



You add view modifiers to control the text’s font, selectability, alignment, layout direction, and so on. These modifiers also affect other views that display text, like the labels on controls, even if you don’t define an explicit [Text](Text.zh-Hans.md) view.

For design guidance, see [doc://com.apple.documentation/design/Human-Interface-Guidelines/typography] in the Human Interface Guidelines.

## Displaying text

- **Text**: A view that displays one or more lines of read-only text.
- **Label**: A standard label for user interface items, consisting of an icon with a title.
- **labelStyle(_:)**: Sets the style for labels within this view.

## Getting text input

- **Building rich SwiftUI text experiences**: Build an editor for formatted text using SwiftUI text editor views and attributed strings.
- **TextField**: A control that displays an editable text interface.
- **textFieldStyle(_:)**: Sets the style for text fields within this view.
- **SecureField**: A control into which people securely enter private text.
- **TextEditor**: A view that can display and edit long-form text.

## Selecting text

- **textSelection(_:)**: Controls whether people can select text within this view.
- **TextSelectability**: A type that describes the ability to select text.
- **TextSelection**: Represents a selection of text.
- **textSelectionAffinity(_:)**: Sets the direction of a selection or cursor relative to a text character.
- **textSelectionAffinity**: A representation of the direction or association of a selection or cursor relative to a text character. This concept becomes much more prominent when dealing with bidirectional text (text that contains both LTR and RTL scripts, like English and Arabic combined).
- **TextSelectionAffinity**: A representation of the direction or association of a selection or cursor relative to a text character. This concept becomes much more prominent when dealing with bidirectional text (text that contains both LTR and RTL scripts, like English and Arabic combined).
- **AttributedTextSelection**: Represents a selection of attributed text.

## Setting a font

- **Applying custom fonts to text**: Add and use a font in your app that scales with Dynamic Type.
- **font(_:)**: Sets the default font for text in this view.
- **fontDesign(_:)**: Sets the font design of the text in this view.
- **fontWeight(_:)**: Sets the font weight of the text in this view.
- **fontWidth(_:)**: Sets the font width of the text in this view.
- **font**: The default font of this environment.
- **Font**: An environment-dependent font.

## Adjusting text size

- **textScale(_:isEnabled:)**: Applies a text scale to text in the view.
- **dynamicTypeSize(_:)**: Sets the Dynamic Type size within the view to the given value.
- **dynamicTypeSize**: The current Dynamic Type size.
- **DynamicTypeSize**: A Dynamic Type size, which specifies how large scalable content should be.
- **ScaledMetric**: A dynamic property that scales a numeric value.
- **TextVariantPreference**: A protocol for controlling the size variant of text views.
- **FixedTextVariant**: The default text variant preference that chooses the largest available variant.
- **SizeDependentTextVariant**: The size dependent variant preference allows the text to take the available space into account when choosing the variant to display.

## Controlling text style

- **bold(_:)**: Applies a bold font weight to the text in this view.
- **italic(_:)**: Applies italics to the text in this view.
- **underline(_:pattern:color:)**: Applies an underline to the text in this view.
- **strikethrough(_:pattern:color:)**: Applies a strikethrough to the text in this view.
- **textCase(_:)**: Sets a transform for the case of the text contained in this view when displayed.
- **textCase**: A stylistic override to transform the case of `Text` when displayed, using the environment’s locale.
- **monospaced(_:)**: Modifies the fonts of all child views to use the fixed-width variant of the current font, if possible.
- **monospacedDigit()**: Modifies the fonts of all child views to use fixed-width digits, if possible, while leaving other characters proportionally spaced.
- **AttributedTextFormattingDefinition**: A protocol for defining how text can be styled in a view.
- **AttributedTextValueConstraint**: A protocol for defining a constraint on the value of a certain attribute.
- **AttributedTextFormatting**: A namespace for types related to attributed text formatting definitions.

## Managing text layout

- **truncationMode(_:)**: Sets the truncation mode for lines of text that are too long to fit in the available space.
- **truncationMode**: A value that indicates how the layout truncates the last line of text to fit into the available space.
- **allowsTightening(_:)**: Sets whether text in this view can compress the space between characters when necessary to fit text in a line.
- **allowsTightening**: A Boolean value that indicates whether inter-character spacing should tighten to fit the text into the available space.
- **minimumScaleFactor(_:)**: Sets the minimum amount that text in this view scales down to fit in the available space.
- **minimumScaleFactor**: The minimum permissible proportion to shrink the font size to fit the text into the available space.
- **baselineOffset(_:)**: Sets the vertical offset for the text relative to its baseline in this view.
- **kerning(_:)**: Sets the spacing, or kerning, between characters for the text in this view.
- **tracking(_:)**: Sets the tracking for the text in this view.
- **flipsForRightToLeftLayoutDirection(_:)**: Sets whether this view mirrors its contents horizontally when the layout direction is right-to-left.
- **TextAlignment**: An alignment position for text along the horizontal axis.

## Rendering text

- **Creating visual effects with SwiftUI**: Add scroll effects, rich color treatments, custom transitions, and advanced effects using shaders and a text renderer.
- **TextAttribute**: A value that you can attach to text views and that text renderers can query.
- **textRenderer(_:)**: Returns a new view such that any text views within it will use `renderer` to draw themselves.
- **TextRenderer**: A value that can replace the default text view rendering behavior.
- **TextProxy**: A proxy for a text view that custom text renderers use.

## Limiting line count for multiline text

- **lineLimit(_:)**: Sets to a closed range the number of lines that text can occupy in this view.
- **lineLimit(_:reservesSpace:)**: Sets a limit for the number of lines text can occupy in this view.
- **lineLimit**: The maximum number of lines that text can occupy in a view.

## Formatting multiline text

- **lineSpacing(_:)**: Sets the amount of space between lines of text in this view.
- **lineSpacing**: The distance in points between the bottom of one line fragment and the top of the next.
- **multilineTextAlignment(_:)**: Sets the alignment of a text view that contains multiple lines of text.
- **multilineTextAlignment**: An environment value that indicates how a text view aligns its lines when the content wraps or contains newlines.

## Formatting date and time

- **SystemFormatStyle**: A namespace for format styles that implement designs used across Apple’s platformes.
- **TimeDataSource**: A source of time related data.

## Managing text entry

- **autocorrectionDisabled(_:)**: Sets whether to disable autocorrection for this view.
- **autocorrectionDisabled**: A Boolean value that determines whether the view hierarchy has auto-correction enabled.
- **keyboardType(_:)**: Sets the keyboard type for this view.
- **scrollDismissesKeyboard(_:)**: Configures the behavior in which scrollable content interacts with the software keyboard.
- **textContentType(_:)**: Sets the text content type for this view, which the system uses to offer suggestions while the user enters text on macOS.
- **textInputAutocapitalization(_:)**: Sets how often the shift key in the keyboard is automatically enabled.
- **TextInputAutocapitalization**: The kind of autocapitalization behavior applied during text input.
- **textInputCompletion(_:)**: Associates a fully formed string with the value of this view when used as a text input suggestion
- **textInputSuggestions(_:)**: Configures the text input suggestions for this view.
- **textInputSuggestions(_:content:)**: Configures the text input suggestions for this view.
- **textInputSuggestions(_:id:content:)**: Configures the text input suggestions for this view.
- **textContentType(_:)**: Sets the text content type for this view, which the system uses to offer suggestions while the user enters text on a watchOS device.
- **textContentType(_:)**: Sets the text content type for this view, which the system uses to offer suggestions while the user enters text on macOS.
- **textContentType(_:)**: Sets the text content type for this view, which the system uses to offer suggestions while the user enters text on an iOS or tvOS device.
- **TextInputFormattingControlPlacement**: A structure defining the system text formatting controls available on each platform.

## Dictating text

- **searchDictationBehavior(_:)**: Configures the dictation behavior for any search fields configured by the searchable modifier.
- **TextInputDictationActivation**
- **TextInputDictationBehavior**

## Configuring the Writing Tools behavior

- **writingToolsBehavior(_:)**: Specifies the Writing Tools behavior for text and text input in the environment.
- **WritingToolsBehavior**: The Writing Tools editing experience for text and text input.

## Specifying text equivalents

- **typeSelectEquivalent(_:)**: Sets an explicit type select equivalent text in a collection, such as a list or table.

## Localizing text

- **Preparing views for localization**: Specify hints and add strings to localize your SwiftUI views.
- **LocalizedStringKey**: The key used to look up an entry in a strings file or strings dictionary file.
- **locale**: The current locale that views should use.
- **typesettingLanguage(_:isEnabled:)**: Specifies the language for typesetting.
- **TypesettingLanguage**: Defines how typesetting language is determined for text.

## Deprecated types

- **ContentSizeCategory**: The sizes that you can specify for content.

## Views

- **View fundamentals**: Define the visual elements of your app using a hierarchy of views.
- **View configuration**: Adjust the characteristics of views in a hierarchy.
- **View styles**: Apply built-in and custom appearances and behaviors to different types of views.
- **Animations**: Create smooth visual updates in response to state changes.
- **Images**: Add images and symbols to your app’s user interface.
- **Controls and indicators**: Display values and get user selections.
- **Menus and commands**: Provide space-efficient, context-dependent access to commands and controls.
- **Shapes**: Trace and fill built-in and custom shapes with a color, gradient, or other pattern.
- **Drawing and graphics**: Enhance your views with graphical effects and customized drawings.

