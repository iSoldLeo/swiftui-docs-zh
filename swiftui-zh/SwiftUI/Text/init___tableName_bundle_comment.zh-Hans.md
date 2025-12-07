--- 来源：https://developer.apple.com/documentation/SwiftUI/Text/init(_:tableName:bundle:comment:)

抓取时间：2025-12-01T02:39:05Z

---

# init(_:tableName:bundle:comment:)

**Initializer**

创建一个文本视图，用于显示由键标识的本地化内容。

## 声明

```swift
init(_ key: LocalizedStringKey, tableName: String? = nil, bundle: Bundle? = nil, comment: StaticString? = nil)
```

## 参数

- **key**：`tableName`标识的表中字符串的键。

- **tableName**：要搜索的字符串表的名称。如果为`nil`，则使用`Localizable.strings`文件中的表。

- **bundle**：包含字符串文件的包。如果为 `nil`，则使用主包。

- **comment**：关于此键值对的上下文信息。

## 讨论

使用此初始化程序在本地化表中查找 `key` 参数，并在已初始化的文本视图中显示关联的字符串值。如果初始化程序在表中找不到该键，或者表不存在，则文本视图将显示该键的字符串表示形式。

```swift
Text("pencil") // Localizes the key if possible, or displays "pencil" if not.
```

当您使用字符串字面量初始化文本视图时，即使您没有像上面的示例那样显式指定表，该视图也会触发此初始化程序，因为它假定您希望对字符串进行本地化。即使您没有为特定字符串提供本地化，您仍然可以获得合理的行为，因为初始化器会显示键，而键通常包含未本地化的字符串。

如果您使用字符串变量而不是字符串字面量初始化文本视图，则视图会触发 [doc://com.apple.SwiftUI/documentation/SwiftUI/Text/init(_:)-9d1g4] 初始化器，因为它假定您在这种情况下不需要本地化。如果您确实想要本地化存储在字符串变量中的值，您可以选择调用 `init(_:tableName:bundle:comment:)` 初始化器，方法是先从字符串变量创建一个 [LocalizedStringKey](../LocalizedStringKey.zh-Hans.md) 实例：

```swift
Text(LocalizedStringKey(someString)) // Localizes the contents of `someString`.
```

如果您有一个不想本地化的字符串字面量，请改用 [init(verbatim:)](init_verbatim.zh-Hans.md) 初始化器。

### 使用 Markdown 为本地化字符串设置样式

如果本地化字符串或备用键包含 Markdown 内容，视图将以适当的样式显示文本。例如，假设一个应用程序的西班牙语本地化文件中包含以下条目：

```swift
"_Please visit our [website](https://www.example.com)._" = "_Visita nuestro [sitio web](https://www.example.com)._";
```

您可以创建一个视图，并将字符串的 Markdown 格式基础语言版本作为本地化键，如下所示：

```swift
Text("_Please visit our [website](https://www.example.com)._")
```

在西班牙语语言环境中查看时，视图将使用字符串文件中的西班牙语文本，并应用 Markdown 样式。

## 创建文本视图

- **init(_:)**：创建一个显示带样式属性内容的文本视图。

- **init(verbatim:)**：创建一个显示未本地化的字符串字面量的文本视图。

- **init(_:style:)**：创建一个实例，使用特定样式显示本地化的日期和时间。

- **init(_:format:)**：创建一个文本视图，显示由相应格式样式支持的非字符串类型的格式化表示。

- **init(_:formatter:)**：创建一个文本视图，显示 Foundation 对象的格式化表示。

- **init(timerInterval:pauseTime:countsDown:showsHours:)**：创建一个实例，显示在指定时间间隔内计数的计时器。


---
source: https://developer.apple.com/documentation/SwiftUI/Text/init(_:tableName:bundle:comment:)
crawled: 2025-12-01T02:39:05Z
---

# init(_:tableName:bundle:comment:)

**Initializer**

Creates a text view that displays localized content identified by a key.

## Declaration

```swift
init(_ key: LocalizedStringKey, tableName: String? = nil, bundle: Bundle? = nil, comment: StaticString? = nil)
```

## Parameters

- **key**: The key for a string in the table identified by `tableName`.
- **tableName**: The name of the string table to search. If `nil`, use the table in the `Localizable.strings` file.
- **bundle**: The bundle containing the strings file. If `nil`, use the main bundle.
- **comment**: Contextual information about this key-value pair.

## Discussion

Use this initializer to look for the `key` parameter in a localization table and display the associated string value in the initialized text view. If the initializer can’t find the key in the table, or if no table exists, the text view displays the string representation of the key instead.

```swift
Text("pencil") // Localizes the key if possible, or displays "pencil" if not.
```

When you initialize a text view with a string literal, the view triggers this initializer because it assumes you want the string localized, even when you don’t explicitly specify a table, as in the above example. If you haven’t provided localization for a particular string, you still get reasonable behavior, because the initializer displays the key, which typically contains the unlocalized string.

If you initialize a text view with a string variable rather than a string literal, the view triggers the [doc://com.apple.SwiftUI/documentation/SwiftUI/Text/init(_:)-9d1g4] initializer instead, because it assumes that you don’t want localization in that case. If you do want to localize the value stored in a string variable, you can choose to call the `init(_:tableName:bundle:comment:)` initializer by first creating a [LocalizedStringKey](../LocalizedStringKey.zh-Hans.md) instance from the string variable:

```swift
Text(LocalizedStringKey(someString)) // Localizes the contents of `someString`.
```

If you have a string literal that you don’t want to localize, use the [init(verbatim:)](init_verbatim.zh-Hans.md) initializer instead.

### Styling localized strings with markdown

If the localized string or the fallback key contains Markdown, the view displays the text with appropriate styling. For example, consider an app with the following entry in its Spanish localization file:

```swift
"_Please visit our [website](https://www.example.com)._" = "_Visita nuestro [sitio web](https://www.example.com)._";
```

You can create a `Text` view with the Markdown-formatted base language version of the string as the localization key, like this:

```swift
Text("_Please visit our [website](https://www.example.com)._")
```

When viewed in a Spanish locale, the view uses the Spanish text from the strings file, applying the Markdown styling.





## Creating a text view

- **init(_:)**: Creates a text view that displays styled attributed content.
- **init(verbatim:)**: Creates a text view that displays a string literal without localization.
- **init(_:style:)**: Creates an instance that displays localized dates and times using a specific style.
- **init(_:format:)**: Creates a text view that displays the formatted representation of a nonstring type supported by a corresponding format style.
- **init(_:formatter:)**: Creates a text view that displays the formatted representation of a Foundation object.
- **init(timerInterval:pauseTime:countsDown:showsHours:)**: Creates an instance that displays a timer counting within the provided interval.

