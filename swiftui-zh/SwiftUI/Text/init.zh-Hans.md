--- 来源：https://developer.apple.com/documentation/SwiftUI/Text/init(_:)

抓取时间：2025-12-02T21:48:15Z

---

# init(_:)

**Initializer**

创建一个文本视图，用于显示带样式的属性内容。

## 声明

```swift
init(_ attributedContent: AttributedString)
```

## 参数

- **attributedContent**：要根据其属性设置样式和显示的带属性字符串。

### 通过组合属性和视图修饰符来格式化文本

使用此初始化器可以根据指定的 [doc://com.apple.documentation/documentation/Foundation/AttributedString] 中找到的属性来设置文本样式。带属性字符串中的属性优先于视图修饰符添加的样式。例如，以下示例中的属性文本显示为蓝色，尽管使用了 [foregroundColor(_:)](../View/foregroundColor.zh-Hans.md) 修饰符将整个外层 [VStack](../VStack.zh-Hans.md) 的文本设置为红色：

```swift
var content: AttributedString {
    var attributedString = AttributedString("Blue text")
    attributedString.foregroundColor = .blue
    return attributedString
}

var body: some View {
    VStack {
        Text(content)
        Text("Red text")
    }
    .foregroundColor(.red)
}
```

SwiftUI 会尽可能将文本属性与 SwiftUI 修饰符结合使用。例如，以下代码创建了粗体红色文本：

```swift
var content: AttributedString {
    var content = AttributedString("Some text")
    content.inlinePresentationIntent = .stronglyEmphasized
    return content
}

var body: some View {
    Text(content).foregroundColor(Color.red)
}
```

### 支持的 Foundation 属性

SwiftUI [Text](../Text.zh-Hans.md) 视图会渲染 Foundation 属性 [doc://com.apple.documentation/documentation/Foundation/AttributeScopes/FoundationAttributes/inlinePresentationIntent] 定义的大多数样式，例如 [doc://com.apple.documentation/documentation/Foundation/InlinePresentationIntent/stronglyEmphasized] 值，SwiftUI 会将其显示为粗体文本。

### SwiftUI 属性

SwiftUI 还在属性作用域 [doc://com.apple.documentation/documentation/Foundation/AttributeScopes/SwiftUIAttributes] 中定义了其他属性，您可以通过属性字符串的 [doc://com.apple.documentation/documentation/Foundation/AttributeScopes/swiftUI] 属性访问这些属性。SwiftUI 属性的优先级高于其他框架的等效属性，例如 [doc://com.apple.documentation/documentation/Foundation/AttributeScopes/UIKitAttributes] 和 [doc://com.apple.documentation/documentation/Foundation/AttributeScopes/AppKitAttributes]。

### Markdown 支持

您可以使用 Markdown 语法创建 `AttributedString`，从而在 `Text` 视图中设置不同段落的样式：

```swift
let content = try! AttributedString(
    markdown: "**Thank You!** Please visit our [website](http://example.com).")

var body: some View {
    Text(content)
}
```

围绕“Thank You!”的 `**` 语法会应用一个值为 [doc://com.apple.documentation/documentation/Foundation/InlinePresentationIntent/stronglyEmphasized] 的 [doc://com.apple.documentation/documentation/Foundation/AttributeScopes/FoundationAttributes/inlinePresentationIntent] 属性。如前所述，SwiftUI 会将其渲染为粗体文本。 “website”周围的链接语法会创建一个 [doc://com.apple.documentation/documentation/Foundation/AttributeScopes/FoundationAttributes/link] 属性，该属性会应用 `Text` 样式来指示这是一个链接；默认情况下，点击或轻触该链接会在用户的默认浏览器中打开链接的 URL。或者，您可以通过在文本视图的环境中放置 [OpenURLAction](../OpenURLAction.zh-Hans.md) 来执行自定义链接处理。

您还可以在本地化字符串键中使用 Markdown 语法，这意味着您可以编写上面的示例而无需显式创建 `AttributedString`：

```swift
var body: some View {
    Text("**Thank You!** Please visit our [website](https://example.com).")
}
```

在应用程序的字符串文件中，使用 Markdown 语法为应用程序的本地化字符串应用样式。当您想要使用 `^[text](inflect:true)` 语法对本地化字符串执行自动语法一致性时，也可以使用此方法。

有关 SwiftUI 中 Markdown 语法支持的详细信息，请参阅 [init(_:tableName:bundle:comment:)](init___tableName_bundle_comment.zh-Hans.md)。

### 应用自定义文本格式定义

使用 [doc://com.apple.SwiftUI/documentation/SwiftUI/View/attributedTextFormattingDefinition(_:)-81jn6] 修饰符，可将自定义 [AttributedTextFormattingDefinition](../AttributedTextFormattingDefinition.zh-Hans.md) 应用于使用此初始化器创建的文本。这将使文本仅应用定义属性范围内的属性，并在显示之前根据定义的值约束约束属性。

定义 [Scope](../AttributedTextFormattingDefinition/Scope.zh-Hans.md) 中列出的自定义属性（其中 [doc://com.apple.documentation/documentation/Foundation/AttributedStringKey/Value] 符合 [TextAttribute](../TextAttribute.zh-Hans.md) 协议）可以在使用 `Text/Layout/Run/subscript(key:)->T?` 观察文本布局时读取，就像使用 [customAttribute(_:)](customAttribute.zh-Hans.md) 修饰符应用的文本属性一样。

## 创建文本视图

- **init(_:tableName:bundle:comment:)**：创建一个文本视图，显示由键标识的本地化内容。

- **init(verbatim:)**：创建一个文本视图，显示未本地化的字符串字面量。

- **init(_:style:)**：创建一个实例，使用特定样式显示本地化的日期和时间。

- **init(_:format:)**：创建一个文本视图，显示由相应格式样式支持的非字符串类型的格式化表示。

- **init(_:formatter:)**：创建一个文本视图，显示 Foundation 对象的格式化表示。

- **init(timerInterval:pauseTime:countsDown:showsHours:)**：创建一个实例，显示指定时间间隔内的计时器。


---
source: https://developer.apple.com/documentation/SwiftUI/Text/init(_:)
crawled: 2025-12-02T21:48:15Z
---

# init(_:)

**Initializer**

Creates a text view that displays styled attributed content.

## Declaration

```swift
init(_ attributedContent: AttributedString)
```

## Parameters

- **attributedContent**: An attributed string to style and display, in accordance with its attributes.

### Format text by combining attributes and view modifiers

Use this initializer to style text according to attributes found in the specified [doc://com.apple.documentation/documentation/Foundation/AttributedString]. Attributes in the attributed string take precedence over styles added by view modifiers. For example, the attributed text in the following example appears in blue, despite the use of the [foregroundColor(_:)](../View/foregroundColor.zh-Hans.md) modifier to use red throughout the enclosing [VStack](../VStack.zh-Hans.md):

```swift
var content: AttributedString {
    var attributedString = AttributedString("Blue text")
    attributedString.foregroundColor = .blue
    return attributedString
}

var body: some View {
    VStack {
        Text(content)
        Text("Red text")
    }
    .foregroundColor(.red)
}
```



SwiftUI combines text attributes with SwiftUI modifiers whenever possible. For example, the following listing creates text that is both bold and red:

```swift
var content: AttributedString {
    var content = AttributedString("Some text")
    content.inlinePresentationIntent = .stronglyEmphasized
    return content
}

var body: some View {
    Text(content).foregroundColor(Color.red)
}
```

### Supported Foundation attributes

A SwiftUI [Text](../Text.zh-Hans.md) view renders most of the styles defined by the Foundation attribute [doc://com.apple.documentation/documentation/Foundation/AttributeScopes/FoundationAttributes/inlinePresentationIntent], like the [doc://com.apple.documentation/documentation/Foundation/InlinePresentationIntent/stronglyEmphasized] value, which SwiftUI presents as bold text.



### SwiftUI attributes

SwiftUI also defines additional attributes in the attribute scope [doc://com.apple.documentation/documentation/Foundation/AttributeScopes/SwiftUIAttributes] which you can access from an attributed string’s [doc://com.apple.documentation/documentation/Foundation/AttributeScopes/swiftUI] property. SwiftUI attributes take precedence over equivalent attributes from other frameworks, such as [doc://com.apple.documentation/documentation/Foundation/AttributeScopes/UIKitAttributes] and [doc://com.apple.documentation/documentation/Foundation/AttributeScopes/AppKitAttributes].

### Markdown support

You can create an `AttributedString` with Markdown syntax, which allows you to style distinct runs within a `Text` view:

```swift
let content = try! AttributedString(
    markdown: "**Thank You!** Please visit our [website](http://example.com).")

var body: some View {
    Text(content)
}
```

The `**` syntax around “Thank You!” applies an [doc://com.apple.documentation/documentation/Foundation/AttributeScopes/FoundationAttributes/inlinePresentationIntent] attribute with the value [doc://com.apple.documentation/documentation/Foundation/InlinePresentationIntent/stronglyEmphasized]. SwiftUI renders this as bold text, as described earlier. The link syntax around “website” creates a [doc://com.apple.documentation/documentation/Foundation/AttributeScopes/FoundationAttributes/link] attribute, which `Text` styles to indicate it’s a link; by default, clicking or tapping the link opens the linked URL in the user’s default browser. Alternatively, you can perform custom link handling by putting an [OpenURLAction](../OpenURLAction.zh-Hans.md) in the text view’s environment.



You can also use Markdown syntax in localized string keys, which means you can write the above example without needing to explicitly create an `AttributedString`:

```swift
var body: some View {
    Text("**Thank You!** Please visit our [website](https://example.com).")
}
```

In your app’s strings files, use Markdown syntax to apply styling to the app’s localized strings. You also use this approach when you want to perform automatic grammar agreement on localized strings, with the `^[text](inflect:true)` syntax.

For details about Markdown syntax support in SwiftUI, see [init(_:tableName:bundle:comment:)](init___tableName_bundle_comment.zh-Hans.md).

### Applying a custom text formatting definition

Use the [doc://com.apple.SwiftUI/documentation/SwiftUI/View/attributedTextFormattingDefinition(_:)-81jn6] modifier to apply a custom [AttributedTextFormattingDefinition](../AttributedTextFormattingDefinition.zh-Hans.md) to text created using this initializer. This will result in the text only applying attributes in the definition’s attribute scope and constraining attributes according to the definition’s value constraints prior to display.

Custom attributes listed in the definition’s [Scope](../AttributedTextFormattingDefinition/Scope.zh-Hans.md), where the [doc://com.apple.documentation/documentation/Foundation/AttributedStringKey/Value] conforms to the [TextAttribute](../TextAttribute.zh-Hans.md) protocol, can be read when observing the text’s layout using `Text/Layout/Run/subscript(key:)->T?`, just as text attributes applied using the [customAttribute(_:)](customAttribute.zh-Hans.md) modifier.

## Creating a text view

- **init(_:tableName:bundle:comment:)**: Creates a text view that displays localized content identified by a key.
- **init(verbatim:)**: Creates a text view that displays a string literal without localization.
- **init(_:style:)**: Creates an instance that displays localized dates and times using a specific style.
- **init(_:format:)**: Creates a text view that displays the formatted representation of a nonstring type supported by a corresponding format style.
- **init(_:formatter:)**: Creates a text view that displays the formatted representation of a Foundation object.
- **init(timerInterval:pauseTime:countsDown:showsHours:)**: Creates an instance that displays a timer counting within the provided interval.

